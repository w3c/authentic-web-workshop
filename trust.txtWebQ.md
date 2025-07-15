# Questionnaire 

Answer these questions using your familiarity with [*Technological Approaches to Improving Credibility Assessment on the Web*](https://www.w3.org/2018/10/credibility-tech/) (Section 4). Consider your tool as a link in the credible web ecosystem. 

1. Logistics. Provide a brief description of your technology, tool, or proposal. How can we contact you? In what time zone are you located? Please link to Github repos, proposals, explainers, or drafts that you’ve written.

The trust.txt system, based on robots.txt and others, is designed to provide visibility to platforms, advertisers, browsers, and anyone else interested a standardized view into the relationships a site may have with other sites and related accounts on other platforms. It also provides a standardized view of other disclosures related to the content of the site.

Contact: Scott Yates, founder and interim Executive Director, [scott@journallist.net](mailto:scott@journallist.net). 202-742-6842. Central Standard Time. 

* Site: [https://journallist.net/](https://journallist.net/)  
* Spec: [https://journallist.net/reference-document-for-trust-txt-specifications](https://journallist.net/reference-document-for-trust-txt-specifications)  
* Extension validator and more: [https://github.com/JournalList](https://github.com/JournalList)  
* IETF Internet Draft: [https://datatracker.ietf.org/doc/draft-org-trust-relationship-protocol/](https://datatracker.ietf.org/doc/draft-org-trust-relationship-protocol/)  
* Approved list of “well-known” URIs: [https://www.iana.org/assignments/well-known-uris/well-known-uris.xhtml](https://www.iana.org/assignments/well-known-uris/well-known-uris.xhtml)  
* ISSN: [https://portal.issn.org/resource/ISSN/3066-2184](https://portal.issn.org/resource/ISSN/3066-2184)  
* Scraper: [https://github.com/brownwolf1355/JournalList](https://github.com/brownwolf1355/JournalList)  
* Chrome extension: [https://chromewebstore.google.com/detail/trust-uri-validator-exten/clpbejijcdcdlpkmjhjejcnbcpimhepd?pli=1](https://chromewebstore.google.com/detail/trust-uri-validator-exten/clpbejijcdcdlpkmjhjejcnbcpimhepd?pli=1)  
* Mozilla extension: [https://addons.mozilla.org/addon/trust-uri-validator-extension/](https://addons.mozilla.org/addon/trust-uri-validator-extension/)  
* Edge addon: [https://microsoftedge.microsoft.com/addons/detail/trust-uri-validator-exten/fhhjccbhhecflopnmmkhcdkcfphilebo](https://microsoftedge.microsoft.com/addons/detail/trust-uri-validator-exten/fhhjccbhhecflopnmmkhcdkcfphilebo)

2. What problem(s) are you trying to solve? What use cases are you addressing? How do you define credibility? Describe the actors involved.

We are trying to solve at least three problems and the associated use cases: 

**First**, a lack of trustworthiness by users or platforms that sites are created for their intended purpose — e.g. providing news – or if they are created to imitate other sites for purposes of grift or propaganda. 

In other words, anyone can put up a site that claims to have news, and they can also claim to have credibility by using branding of established news organizations. A user may not be able to tell if a site is part of an established brand. In addition, platforms lack tools to determine the credibility of sites, and so may surface non-credible sites as being credible, and de-emphasize sites that are in fact credible, but are so small and underresourced that they appear to platforms to lack credibility.

**Second**, a lack of trustworthiness that social media pages are associated with the organization that they claim.

The use case here is that malicious actors create social media profiles and pages that claim to be managed by established news brands, when in fact they are only created to take advantage of the implied credibility of those brands. The platforms and the brands may not even know this is happening, and users on the internet have no way of knowing if a social media page is actually associated with a brand or not.

**Third**, the lack of an ability for a website publisher to make an affirmative declaration about their relationship with AI training robots.

The use case here is that publishers of sites do not have a simple, site-wide tool to make a declaration of how they want their content to be ingested, indexed and consumed by robot agents of AI companies.

**How do we define credibility?**  As the organization that manages the trust.txt specification document, we have decided not to make any claims about credibility, trustworthiness, or truthfulness of any content. The specification makes it possible to make declarations about relationships between organizations, and declarations about the content by the publisher, and nothing more.

3. Explain the chain of events that help assess credibility in your tool. What architectural choices have you made that enable this?

The chain of events typically is this:

First, an association publishes a trust.txt file listing the active and valid members.  
Second, a website owner publishes a trust.txt file listing the associations that it belongs to, along with the social media pages it controls and a declaration of its message to AI training robots.  
Third, platforms ingest this data to make determinations of the credibility of the publisher.  
Fourth, optionally, users can install a browser extension to be able to independently verify that claimed relationships actually exist.

4. Which role(s) does your proposal fill in the ecosystem (noting that some tools fill multiple roles):  
* Content Consumer - Person receiving the information (audience, reader)  
* Content Provider/Source - Person(s) or organizations delivering content  
* Content Promoter - Person(s) or organization that amplify the spread of information  
* Credibility Facilitator - Person(s) or organization who is helping the consumer decide what to trust.  
* Platform - Technological system, and by extension the person or organization who maintains and controls it.

This tool fills a role that works as a machine-readable file for all of the above.

* **Content Consumer**  
  Consumers won’t interact with the trust.txt file unless they look for it, but they’ll just have better feeds of news because the trust.txt system will strengthen local news publishers who provide news that is always shown to be more trustworthy than national or international news.  
* **Content Provider/Source**  
  The idea is that content providers who belong to industry associations, and follow the rules of those associations, will be strengthened and be able to provide more trustworthy content.  
* **Content Promoter**  
  These promoters will have an increased confidence that they are promoting content that is legitimately associated with the brands that produced it, and not by scammers claiming the brand association falsely.  
* **Credibility Facilitator**  
  The trust.txt system gives those examining content and publishers and easy and uniform place to evaluate the associations and declarations of publishers.  
* **Platform**  
  The trust.txt system gives them a machine readable file to evaluate credibility of sites. Having the file doesn’t automatically imply credibility, but the associations claimed in total can either add or subtract credibility. That is, if a small publisher is a member of a well known press association, that would add credibility.

5. Which [technical approaches](https://www.w3.org/2018/10/credibility-tech/#h.32pkwj5grlt3) do you enable? Are there other ecosystem players that enable the technical approaches with which you will interoperate? Please elaborate  
* Inspection of credibility signals  
* Corroboration of facts, signals  
* Reputation. This can include provenance of the chain of providers, verified trust seals.  
* Transparency requires the information provider to disclose information about themselves and their content.

All of the above. 

With trust.txt files in place, platforms and users can inspect claims of association, corroborate them, make decisions about reputation based on those corroborated claims, and then all can have transparency into all claimed relationships.

6. Describe how your technology, tool, or proposal works from a technical perspective.

The only technical requirement is an ability to place a trust file at the root level of a domain.

The technical approach is simple, a website publisher only needs to place a text file at the root directory.

For most users, the experience will be unseen. The user will, however, have an overall experience of consuming more trustworthy data because the platforms will have a credibility signal that is not currently available to them. Some advanced users may want to take an additional step of installing a browser extension so that they can independently verify claims of association.

7. Describe the user experience and the user research that went into development

For most users, the experience will be invisible, but that user will still benefit because there is a lower likelihood that the user will encounter a site or a social media page that is intended to deceive the user into believing that user is interacting with a trusted, brand-name page or content that is generated with the intent to be deceptive

A tool that has recently become available is a browser extension that allows a user to verify if a page is actually associated with another site in the way that is claimed.

8. Provide any research or evidence supporting the effectiveness of your tool.

Audited Media, which provides tools for marketers hoping to place ads effectively on websites, has incorporated trust.txt files as a part of its evaluation of sites.

Other evidence is anecdotal at the moment, but by its nature the trust.txt system lends itself to systematic review.

9. What aspects of your proposal would benefit from being standardized? With which systems does it need to interoperate? How will this fit into existing technical and social systems (e.g. browser extension, peer review)?

If the W3C were to adopt trust.txt in the way that it adopted [Web Authentication](https://www.w3.org/TR/webauthn/), it could drive adoption and solve the chicken/egg problem associated with relatively modest implementation across the internet. 

As for a browser extension, yes, this is ideally suited to be incorporated into browsers, and we already have an extension built that is based on the trust.txt system.

10. Create a threat model for your technology, tool, or proposal. Are there potential unintended consequences, such as enabling censorship or increasing bias? What are potential attack vectors? What can be done to mitigate these risks?

One risk is that people will associate the existence of a trust.txt file with trustworthiness. Any publisher can post a trust.txt file in the same way that any publisher can publish a badge that the site is approved by the Better Business Bureau or anyone else. The value of the trust.txt file is in making transparent the relationships between the publisher and associations, and being able to verify those relationships. It will be up to the algorithms of the platform, or the user, to determine if the claimed association is valid and if it imputes trust. That is, if the Associated Press claims to be a member of the IPTC, that may be determined to be a positive signal, but if a site has a trust file and claims no memberships at all, that may be interpreted as neutral or even as a negative indicator of credibility.

11. What do you hope for from this W3C effort?

That the W3C will help establish trust.txt as a recognized web standard, ensuring a structured and scalable way to convey site affiliations and credibility signals across the internet. 

By formalizing trust.txt through W3C, we can:

* Increase adoption by giving it the legitimacy of a web standard.  
* Ensure interoperability with other web technologies and metadata frameworks.  
* Improve discoverability by making it easier for search engines, aggregators, and marketers to verify publisher relationships.  
* Promote transparency by giving site publishers a simple way to disclose their affiliations.
