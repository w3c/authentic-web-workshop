# Authentic Web Workshop Questionnaire: Trustnet

Answer these questions using your familiarity with __<a
href="https://www.w3.org/2018/10/credibility-tech/">Technological Approaches to Improving
Credibility Assessment on the Web</a>__ (Section 4). Consider your tool as a link in the credible
web ecosystem.

## 1. Logistics. Provide a brief description of your technology, tool, or proposal. How can we contact you? In what time zone are you located?

Trustnet is a tool that lets people identify a list of people and other entities that they trust,
and then tells them which websites and articles their network thinks are credible.

We are in US East, Central, and West time zones.

Emails: karger@mit.edu, jyasskin@google.com

### Please link to Github repos, proposals, explainers, or drafts that you’ve written.

Trustnet is currently developed in 4 Github repositories:

* https://github.com/farnazj/Trustnet-Backend: server hosting trust information and credibility assessments
* https://github.com/farnazj/Trustnet-Client: prototype social application that leverages trusted credibility assessments to filter content in the user's news feed
* https://github.com/farnazj/Trustnet-Extension: browser extension that leverages trust to inform people about content in place wherever they encounter it as they browse the web
* https://github.com/farnazj/Reheadline-Extension: browser extension that lets users change article headlines in place for people who trust them

## 2. What problem(s) are you trying to solve? What use cases are you addressing?

There is a lack of affordances for recording and leveraging *trust* on the web.  Beyond the very
limited amount of information that a person can determine to be credible based on their own
eyewitness knowledge or reasoning from it, a user's beliefs depend at the root on the information
and credibility assessments they receive from trusted facilitators—whether those facilitators
are individuals, organizations, or even the platforms delivering the information through applications.
Because trust is fundamental to credibility assessment, we have to do a better job of capturing and
leveraging each user's choices about what facilitators they trust.

We also need to do a better job of surfacing this information at the right time.  Although there
are many ways to laboriously investigate the credibility of an article, we need to make it much
easier for anyone to know at a glance whether an article they are reading is credible.

### How do you define credibility?

We define credibility for a particular user as endorsement by other entities who that user has marked as
trusted.

### Describe the actors involved.

The primary actors are:
* Facilitators (referred to as sources in Trustnet), who rate web pages and other trust facilitators for trustworthiness, and expose those
  ratings for consumers to rely on.
* Consumers who express trust in particular facilitators and can easily see which pages those facilitators
  rate as trustworthy or untrustworthy.
* Trust aggregators, who make it easy to find trust signals for a given page, protect the privacy of
  end-users, and (optionally) identify new trust facilitators who agree with an end-user's independent
  trustworthiness assessments.

Many consumers are expected to also be trust facilitators, especially for their friends and relatives.
There is currently just one trust aggregator in the implemented system, but ideally this wouldn't be
a centralized role.

## 3. Explain the chain of events that help assess credibility in your proposal. What architectural choices have you made that enable this?

We recognize that all assessments of credibility are based on (i) direct verification entirely 
from personal knowledge, which is often
impossible, or (ii) trust in some other entities that provide information necessary to verify.
While trusted entities might provide supporting evidence or argumentation which is assessed by the
consumer, we focus on the most direct application: an architecture that enables trusted facilitators to
share their credibility assessments however generated, and that allows consumers to fetch and
aggregate the credibility assessments by those trusted facilitators.

Core assumptions are that (i) it is not possible to establish universally trusted facilitators of
credibility assessment and therefore (ii) every individual should be able to make their own
decisions about which facilitators they wish to trust.   This specifically opposes approaches that assume
that platforms can be trusted to provide credibility assessments to consumers who may not trust
those platforms.

Because we wish to support credibility assessment everywhere on the web, we have explored
architectures that can enable credibility assessments on arbitrary web pages (URLs) rather than
platforms that only assess the content “on” those platforms.   Because we believe effective
credibility assessment cannot interrupt the flow of a user’s activity, we inject credibility
assessments directly into web pages via a browser extension, instead of sending the user elsewhere
to assess credibility.

The chain of events for credibility assessment are:
1. every individual indicates which facilitators—individuals or organizations—they trust.
1. any facilitator can record credibility assessments on any url
1. when a consumer visits a url or encounters it in a feed,
   tools fetch and aggregate any assessments for that url made by facilitators the user trusts
1. based on the aggregation, the tool presents an aggregate credibility assessment *in place* as the user views the article or news feed.

## 4. Which role(s) does your proposal fill in the ecosystem (noting that some tools fill multiple roles):

* Credibility Facilitator - Person(s) or organization who is helping the consumer decide what to trust.
* Platform - Technological system, and by extension the person or organization who maintains and controls it.

## 5. Which <a href="https://www.w3.org/2018/10/credibility-tech/#h.32pkwj5grlt3">technical approaches</a> do you enable?

* Inspection of credibility signals
* Reputation. This can include provenance of the chain of providers, verified trust seals.
* Transparency requires the information provider to disclose information about themselves and their content.

Fundamentally, Trustnet provides a *personalized* credibility signal for each piece of content based on an aggregation of assessments from
*personally*-trusted facilitators. The extension makes
it easy to inspect the trusted assessments on links or pages, and the system is transparent about how assessments
was aggregated, and which trusted facilitators might disagree with the user's considered opinion.

### Are there other ecosystem players that enable the technical approaches with which you will interoperate?

Not yet.

## 6. Describe how your technology, tool, or proposal works from a technical perspective.

The extension binds assessments of content to URLs and uses URLs to find assessments for content.
Because any piece of content appearing in a social feed but coming from a different facilitator typically
has a URL of its own (e.g., tweets, Youtube videos, comments), this approach enables separate
assessment of each post in a feed.

When a user is on a web page, the extension checks the URL (and its variations) to see whether its
associated content has been assessed by facilitators the user trusts or follows (other individuals or
entities such as fact checking orgs or news publishing media). If there are such assessments for the
page, an aggregate assessment can be displayed by the corner of the page, and optionally
a pane that contains the assessments can pop open on the side of the page automatically. However,
many resources whose accuracy needs to be signalled are usually embedded into a feed or are
presented as links on an aggregator page and prior work has reported that links are often not
clicked even when they are shared. Therefore, it is important to surface credibility signals in
situ—directly within the feed or page the user is browsing—so that assessments are visible at the
point of exposure, not just upon visiting the linked content.

The extension scans the page for all URLs on the page and queries our server for any stored
assessments by those the user follows or trusts. It then slightly modifies the rendered DOM to place
an icon indicating the accuracy status of the link’s associated resource next to each URL. We
additionally made the design decision to reduce the salience of links assessed as inaccurate by
making them look faded.

Before requesting assessments, URLs have to be canonicalized by stripping irrelevant query
parameters and following redirects. The extension strips all but an allow-list of query parameters
and then follows redirects on the client before caching those redirects on the server.

The extension sets up a mutation observer to monitor the page for dynamic changes (e.g., infinite
scroll) and fetches assessments for any newly loaded links. Users can also configure a blocklist of
domains where they don’t want the extension to run, via an Options page.

## 7. Describe the user experience and the user research that went into development.

We developed the approach based on our research on:

1. Need-finding studies to investigate what signals should be provided to users to support them in
   content credibility seeking and providing practices that they are already engaging in, but
   without structured support, and often despite the current structures undermining their efforts.
   We observed that users need a channel for assessing content accuracy for the benefit of their
   social circle and receiving assessments from those they trust (as they currently attempt to
   repurpose, with uncertain efficacy, features provided for other purposes), and they need to
   indicate who they consider trustworthy separately from the facilitators they would want to see content
   from: [Leveraging Structured Trusted-Peer Assessments to Combat
   Misinformation](https://dl.acm.org/doi/pdf/10.1145/3555637)
2. Development of a research prototype social media platform prototype that offers these affordances, and
   evaluating it longitudinally with participants who joined the platform with others from their
   social circle: [Leveraging Structured Trusted-Peer Assessments to Combat
   Misinformation](https://dl.acm.org/doi/pdf/10.1145/3555637)
3. Development of the Trustnet extension that offered these signals in-situ on the web and a
   longitudinal evaluation of the extension with a set of users: [A Browser Extension for in-place
   Signaling and Assessment of Misinformation](https://dl.acm.org/doi/pdf/10.1145/3613904.3642473)
4. Our research on the phenomenon that drawing users’ attention to accuracy reduces their likelihood
   of sharing misinformation: [Exploring Lightweight Interventions at Posting Time to Reduce the
   Sharing of Misinformation on Social Media](https://dl.acm.org/doi/pdf/10.1145/3449092)
5. Development of the Reheadline browser extension that enables users to modify problematic content
   for the better and its longitudinal evaluation. This extension focuses on news headlines and allows users to suggest alternative
   headlines for news articles. This is a user-centered approach intended to involve users in
   combating misleading headlines or clickbaits. Other users who follow the headline suggester will
   see the suggested alternative headline next to the original wherever on the web that the
   original headline appears.
6. Development of a personalized AI system to address the scale limitations of user-driven assessments by predicting 
   how a user would assess unseen content based on their prior judgments, and a user study exploring its use and
   unintended consequences. This approach enables users' assessments on one instance of a claim to generalize
   across similar posts published by different sources: [Exploring the Use of Personalized AI for Identifying 
   Misinformation on Social Media](https://dl.acm.org/doi/pdf/10.1145/3544548.3581219) 

## 8. Provide any research or evidence supporting the effectiveness of your tool.

* [Leveraging Structured Trusted-Peer Assessments to Combat Misinformation](https://dl.acm.org/doi/pdf/10.1145/3555637)
* [A Browser Extension for in-place Signaling and Assessment of Misinformation](https://dl.acm.org/doi/pdf/10.1145/3613904.3642473)
* [Our Browser Extension Lets Readers Change the Headlines on News Articles, and You Won’t Believe What They Did!](https://dl.acm.org/doi/pdf/10.1145/3555643)
* [Exploring Lightweight Interventions at Posting Time to Reduce the Sharing of Misinformation on Social Media](https://dl.acm.org/doi/pdf/10.1145/3449092)
* [Exploring the Use of Personalized AI for Identifying Misinformation on Social Media](https://dl.acm.org/doi/pdf/10.1145/3544548.3581219)

## 9. What aspects of your proposal would benefit from being standardized? With which systems does it need to interoperate? How will this fit into existing technical and social systems (e.g. browser extension, peer review)?

Ideally, trust facilitators could publish their assessments in a way that could be consumed by multiple
trust aggregators, and end-users could consume those assessments either directly or through their
choice of aggregators. That implies standardized protocols for facilitator<->aggregator and
aggregator<->user communication.  There may also be efficiency opportunities in standards that permit a 
content source to embed assessments directly in the content (in a trustworthy way), 
turning the content source itself into an aggregator.

Browsers (or extensions in them) need to be able to display assessments on links. Since modern
social networking sites display a block of content instead of just an `<a>` tag, we need a standard
way of identifying the block that needs to be annotated. There's no existing cross-site convention
for this.

Assessments are bound to URLs, but redirects, query parameters, and user-personalized URLs can all create vast numbers of 
distinct URLs for the same content.   There is a standard for indicating the "canonical" URL for a piece
of content—[`<link rel=canonical>`](https://html.spec.whatwg.org/multipage/links.html#link-type-canonical)—whose integrity is reinforced by its effect on search rankings.
However, as the Trustnet use may produce the opposite incentive for some content providers, work may be needed to maintain the signal.

As a general perspective on standards, if we are able to pivot towards a web where content without assessments is ignored by user agents, 
that would provide a strong incentive for content provides to embed trusted assessments directly in their content.   If we remain with 
the current web where content is generally trusted *unless it is assessed false*, the providers have incentives *against* providing standardized
assessments.

## 10. Create a threat model for your technology, tool, or proposal. What are potential attack vectors? What can be done to mitigate these risks?

_This section contains speculation about the system's dynamic behavior, which ought to be validated by future research._

Entities ranging from individual content creators up to nation-states have an interest in telling end-users that particular content either is or is not trustworthy. We assume that these attackers can create an unlimited number of sockpuppets and have those sockpuppets rate content in any way they want. To manipulate the trustworthiness shown to any individual end-user, the attacker needs to control a significant fraction of that user's trusted sources, which requires convincing the end-user to mark the attacker's sockpuppets as trustworthy. This is likely to happen by agreeing with the end-user's independent assessments a significant fraction of the time, which requires being honest about most ratings during that time. After getting "enough" subscribers, the attacker can change strategies to publish dishonest ratings.

When an end-user's trust facilitators disagree about a page, the tool shows that fact. Since users are
likely to still have a significant fraction of honest trust facilitators, this gives them a prompt to
discover that the attacker's sockpuppets have become unreliable so that the end-user can remove them
as trust facilitators and end the attack.

Another avenue of attack is to buy widely-used trust facilitators. Again, as long as attackers can't buy
a supermajority or all of an end-user's facilitators, the user will see the disagreement among their
facilitators, which will prompt them to mark these compromised facilitators as no-longer-trusted.

Attackers can exploit the fact that link canonicalization is done on the client and then cached on
the server. This optimization has been useful in bootstrapping the system, but there's a good chance
we'll need to abandon it once someone decides to attack it.

Another attack is for an adversary to take control of a consumer's trust aggregator which records and disseminates trust assessments.  

### Are there potential unintended consequences, such as enabling censorship or increasing bias?

The primary unintended consequence of this system is in reinforcing echo chambers. However, most
people know personally some other people who are outside of their primary echo chamber, and are
likely to mark them as trusted, even if they often disagree about the trustworthiness of web pages.
These divergent trust facilitators can prompt people to think harder about particular articles, and
thinking harder is what breaks people out of echo chambers.  Independently, there is an argument based in
personal autonomy that people should have a right to create echo chambers if they wish to do so.


## 11. What do you hope for from W3C in this effort?

We're looking for other people interested in working in this direction, and in help finding
consensus on any standards that are useful.
