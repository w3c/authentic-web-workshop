Authentic Web Workshop Questionnaire: C2PA


# Questionnaire

Answer these questions using your familiarity with [Technological Approaches to Improving Credibility Assessment on the Web](https://www.w3.org/2018/10/credibility-tech/) (Section 4). Consider your technology as a link in the credible web ecosystem.

**1. Logistics. Provide a brief description of your technology, tool, or proposal. How can we contact you? In what time zone are you located? Please link to GitHub repos, proposals, explainers, or drafts that you’ve written.**

- C2PA Specification: <https://c2pa.org/specifications/specifications/2.1/index.html>

* C2PA Explainer: <https://c2pa.org/specifications/specifications/1.4/explainer/Explainer.html>

- C2PA User Experience Guidance for Implementers: <https://c2pa.org/specifications/specifications/1.1/ux/UX_Recommendations.html>

- C2PA Security Considerations: <https://c2pa.org/specifications/specifications/1.4/security/Security_Considerations.html>

- C2PA Harms Modelling: <https://c2pa.org/specifications/specifications/1.4/security/Harms_Modelling.html>

- CAWG Identity Assertion: <https://cawg.io/identity/1.1-draft/>

- CAWG Endorsement Assertion: <https://cawg.io/endorsement/1.0-draft/>

- CAWG Metadata Assertion: <https://cawg.io/metadata/1.1-draft/>

- CAWG Training and Data Mining Assertion: <https://cawg.io/training-and-data-mining/1.1-draft/>

- IPTC Origin Verified News Publishers List: <https://iptc.org/verified-news-publishers-list/>

- IPTC Media Provenance Policy: <https://iptc.org/media-provenance/iptc-media-provenance-policy-overview/>

We are in the process of publishing a 2.2 update for many of these documents, so please look for newer versions prior to the meeting.

**2. What problem(s) are you trying to solve? What use cases are you addressing? How do you define credibility? Describe the actors involved.**

From the [C2PA Explainer](https://c2pa.org/specifications/specifications/1.4/explainer/Explainer.html): 

In an era where digital media (e.g., images, videos, audio and documents) is easily created and manipulated, whether by humans or generative AI, it is important for users to be able to verify the authenticity and provenance of such media to prevent them from being misled or harmed. These concerns have been raised across journalism, social media, and other industries that rely on trust and authenticity. The Coalition for Content Provenance and Authenticity ([C2PA](https://c2pa.org)) was formed to address these challenges by developing an open standard that enables creators, publishers, and consumers to verify the origins and history of digital content.

The goal of the C2PA Specifications for Content Credentials is to tackle the extraordinary challenge of trusting media in the context of rapidly evolving technology and the democratization of powerful creation and editing techniques. To this end, the C2PA specifications are designed to enable global, opt-in adoption of digital provenance techniques through the creation of a rich ecosystem of digital provenance-enabled applications for a wide range of individuals, organizations and devices, while meeting appropriate security and privacy requirements, as well as human rights considerations.

Provenance, as C2PA defines it, refers to the facts about the history of a piece of digital content (also known as an asset) in a form such as an image, video, audio recording, or document. At the heart of the C2PA specification is the Content Credential, a cryptographically bound structure that records an asset’s provenance. Content Credentials, also known as a C2PA Manifest, contain one or more assertions, which are statements about the asset, such as its origin (i.e., when and where it was created), modifications (i.e., what happened using what tools) and use of AI (i.e., how it was authored). While C2PA defines a set of assertions, it also allows others to add their own. These may include assertions about who created the content, whether they wish to allow its use for AI training or industry-specific information such as supply chain info.

It is important to highlight that Content Credentials do not provide value judgments about whether a given set of provenance data is 'true', but instead merely whether the provenance information is well-formed and free from tampering, valid and trusted (in that the signer of the Content Credential is associated with a known trust list). In addition, the provenance information can be verified as associated with the underlying asset ("a valid asset").

It is not a cure-all for misinformation, but instead seeks to mitigate against its threats in the digital domain. It complements media literacy, fact-checking, and digital forensics approaches such as deep-fake detection by providing an infrastructure to record all of that information in a tamper-evident structure, representing the provenance of any asset.

Some use cases:

- Content Consumer

  - Alice sends a video to a friend, Bob. The video includes text with alarming and controversial allegations. Bob immediately seeks confirmation of its validity, starting with its provenance. The video that Alice sent contains C2PA provenance. With a C2PA-enabled application, Bob is able to establish that this video has been validated as being published by an organisation he can trust and is held in public high regard.

- Journalist (Content Source)

  - A photojournalist uses a C2PA-enabled capture device during a newsworthy event they are covering. The assets are then brought into a C2PA-enabled editing application, and after editing it, they are sent to a photo editor. The editor makes additional edits also using a C2PA-enabled application. The finalized asset is moved into the content management system of a news organization, which is also C2PA-enabled, before posting the asset to social media.

- Journalist or Fact Checker (Content Consumer)

  - An important news event happens and there is a lot of media coverage that reporters want to go through. Reporters connect to a C2PA-enabled media portal and are able to use aspects of the media and its provenance to run queries such as: 

    - Find all assets from any identified source, or a particular set of sources

    - Find all assets from the square kilometre with these central coordinates

    - Find all assets created between time 'x' and 'y'

- Citizens (Content Source)

  - A human rights defender manages to capture footage containing C2PA-enabled provenance of police violence during a protest. The human rights defender sends the footage to a human rights organization that verifies that the asset meets video-as-evidence criteria. The human rights organization redacts information about the defender using a C2PA-enabled editing application in order to protect their identity. The C2PA-verified asset is then used to improve the chances of that footage being admissible in court proceedings.

- News Publisher (Content Provider)

  - A news organization publishes an image and/or video asset signed by the publisher, along with publisher-specified metadata such as when the asset was published, the news article to which the content is associated and work undertaken to fact-check the content. Users can examine the signed metadata to see more information about how the news organisation checked the asset (even if it wasn’t “born” with C2PA metadata) and why the decided to use this particular asset to illustrate the news story.

  - A piece of C2PA-signed news content is re-posted on social media in an attempt to manipulate consumers into thinking that the asset depicts a breaking news event. Through examining the signature and signed metadata, consumers can detect that the asset is being “miscontextualized”, i.e. used in an incorrect context, and that the asset was actually associated with a different news event.

  - A journalist receives a C2PA-signed asset from a photojournalist in a war zone. It is critical that metadata such as GPS location is removed from the content, and that some faces are blurred, before publishing. The picture editor in the newsroom, while editing the asset, performs a C2PA “redaction” operation which scrubs chosen metadata fields and removes thumbnails from older versions of the content, while keeping the C2PA signature chain intact.

- Social Media Platforms (Content Provider / Platform)

  - A news video is posted to a social media platform. By utilizing the C2PA-enabled provenance in the video, the social media platform is able to verify that it came from the same source that posted it.

- Open Source Intelligence (Content Consumer)

  - An individual in a news/other context using open-source intelligence techniques (OSINT) can use the presence of C2PA provenance in assets to better confirm the history and integrity of media. Additionally, an individual may use a decoupled binding database to re-correlate relevant media to its C2PA provenance.

**3. Explain the chain of events that help end users assess credibility in your technology, tool, or proposal. What architectural choices have you made that enable this?**

From the [C2PA Explainer](https://c2pa.org/specifications/specifications/1.4/explainer/Explainer.html):

NOTE: The use of the term “authentic” here simply means that the information comes from exactly where the technical mechanism says it does. Untrustworthy or “fake” information can be authentic, in that the consumer understands where that information comes from. Sources of information can make claims within that information (such as within free-text assertions) that attempt to mis-attribute or deceive. The primary two mechanisms that provide the technical authenticity mechanism are C2PA Manifest Signatures and CAWG Identity Assertion signatures.

The C2PA specification for Content Credentials provides a standardized method for attaching Content Credentials, which can be validated, to digital assets. Here’s how it works:

1. Content Creation: A creator uses a Content Credentials-enabled tool to produce and/or publish digital content, such as a photograph or video. During this process, provenance information is generated, including a cryptographic signature and possibly including additional details about the creator, the device used, and any applied edits.

2. C2PA Manifest Generation: The provenance information is encoded into a data structure called a C2PA Manifest, also known as a Content Credential. This C2PA Manifest can contain variety of assertions representing the provenance of the asset, including:

   - A description of the asset’s origin.

   - Details of any modifications or edits.

   - Information about the publisher of the asset

   - Background information on how the asset was verified and fact-checked 

   - A cryptographic hash representing the content at the time of manifest creation.

3. Cryptographic Signing: The C2PA Manifest is signed with the private key of the entity (software, hardware or organization) that performed the operations, thus ensuring its authenticity and integrity. The corresponding public key is made available for verification.

4. Embedding, referencing, and optional "soft binding": The C2PA Manifest is commonly embedded directly within the asset, but the Manifest can also be stored externally, and a reference to it added to the asset metadata. It can also be linked externally through an optional soft binding system (e.g., invisible watermarks, digital fingerprints). This can help make the provenance information accessible if the embedding or reference is lost.

5. Distribution: The asset, along with its embedded C2PA Manifest, is distributed via platforms like social media, news sites, or file-sharing services. The C2PA Manifest travels with the asset, ensuring that media is able to be independently validated, and that any further use of the asset can retain its provenance history.

6. Verification: When an end user views or interacts with an asset using a Content Credential-enabled application, the application verifies the integrity of the C2PA Manifest and its associated asset. It can confirm that the asset has not been modified since the C2PA Manifest was created, and that the provenance information inside is also unmodified and authentic to the Signer of the Manifest. In scenarios where the Signer can chain to the C2PA Trust List, Consumers and Validators can optionally extend their trust to the implementation that signed it.

7. Presentation: When presented to a user, verified content will be marked with a clear indicator, such as a badge or icon, signalling to the user that the provenance information in the asset is authentic and intact. In itself, the presence of the indicator can't be used by users to make trust decisions: it indicates the presence of authentic provenance data that may help to make those decisions.

On CAWG: CAWG builds on the C2PA’s Content Credentials spec with a number of new assertions. Most relevant to this discussion is the Identity Assertion, which provides another means for an actor to identify themselves as having a role in the production of an asset. In the above flow, it fits in around 3, where additional digital signatures are added to the asset. Use cases for this include the ability for individuals and organisations to specify their involvement in an asset.

On IPTC: The [IPTC’s Verified News Publisher programme](https://iptc.org/verified-news-publishers-list/) is an effort to build a list of news organisations whose identity has been vetted, to allow them to sign their content with a certificate that is known to represent a verified publisher. News organisations such as Agence France-Presse, BBC, CBC/Radio-Canada, Deutsche Welle, WDR and France Televisions are publishing signed (test) content using Verified News Publisher certificates today. The IPTC operates a C2PA validator, <https://originverify.iptc.org/>, that checks C2PA signatures against both the main C2PA Trust List and the IPTC Verified News Publishers List.

By adding a publisher to the Verified News Publishers List, the IPTC only asserts that the identity of the organisation has been checked. A Verified News Publisher certificate in itself does not assert that any type of audit or vetting was conducted regarding the trustworthiness of the publisher or of the content published, although the IPTC is working with organisations such as [The Trust Project](https://thetrustproject.org/) and the [Journalism Trust Initiative](https://www.journalismtrustinitiative.org/) to allow their “trust indicators” to be conveyed to consumers and platforms via C2PA assertions embedded in publisher-signed assets.

**4. Which role(s) does your proposal fill in the ecosystem (noting that some tools fill multiple roles):**

- Content Consumer - Person receiving the information (audience, reader)

- Content Provider/Source - Person(s) or organizations delivering content

- Content Promoter - Person(s) or organization that amplify the spread of information

- Credibility Facilitator - Person(s) or organization who is helping the consumer decide what to trust.

- Platform - Technological system, and by extension the person or organization who maintains and controls it

C2PA by itself acts as a Credibility Facilitator. It is used by Content Consumers and implemented by Content Providers/Sources, and Platforms (which could be the web platform, or social media platforms or websites in general)

**5. Which** [**technical approaches**](https://www.w3.org/2018/10/credibility-tech/#h.32pkwj5grlt3) **do you enable? Are there other ecosystem players that enable the technical approaches with which you will interoperate? Please elaborate.**

- Inspection

- Corroboration

- Reputation

- Transparency

C2PA is primarily a Transparency mechanism. From the [Technological Approaches to Improving Credibility Assessment on the Web, Section 10.4](https://www.w3.org/2018/10/credibility-tech/#h.uczdbpambvtx):

_Here, the emphasis shifts toward the provider making an effort to be more visibly trustworthy. Transparency requires the provider reveal information about themselves and their content, which can require considerable effort and often brings significant risk, in the hope of being more credible._

C2PA enables creators and publishers to verifiably show how images and media content has been created, from capture through editing to publication. This includes labelling AI-generated or wholly human authored content as such.

Although C2PA is not a reputation system in itself, in that it does not enable a website or content-level reputation scoring system, but these parts of the Reputation description fit well, from [Section 10.3](https://www.w3.org/2018/10/credibility-tech/#h.41t1lbapkm9n):

_1. Make the identity of the content provider, including any provenance chain of providers behind them, visible to the consumer, especially in ways which align with user’s natural skills at recognizing faces and logos. In particular, systems could try to avoid presenting confusingly similar brands without clear warning, and indicating how familiar their data indicates the brand is to the user._

_5. Make trust seals and other positive reputation signals from institutions secure. Some trust seals (like_ [_the one from BBB_](https://www.bbb.org/lexington/for-businesses/about-bbb-accreditation/for-accredited-businesses/bbb-dynamic-seal/)_) are more than just_ [_an embedding image that anyone can use_](https://www.howtogeek.com/199240/all-those-seals-of-approval-on-websites-dont-really-mean-anything/)_, but many are not. Even the more secure ones can be abused to mislead users who do not check them. In contrast, an out-of-band secure solution, for example done by the browser, could be much more secure._

**6. Describe how your tool works technically.**

See Q3.

**7. Describe the user experience and the user research that went into development.**

See [Examining the Impact of Provenance-Enabled Media on Trust and Accuracy Perceptions](https://dl.acm.org/doi/10.1145/3610061) in Proceedings of the ACM on Human-Computer Interaction, Volume 7, Issue CSCW2.

And [Does provenance build trust?](https://www.bbc.co.uk/rdnewslabs/news/does-provenance-build-trust), BBC News Labs, 24 May 2024.

IBC/IET tech paper from the BBC and Media Cluster Norway: <https://www.theiet.org/media/13ffysxm/the-best-of-iet-and-ibc-2024.pdf> (pp 35-39)

See Behind the design: Adobe Content Authenticity app: <https://adobe.design/stories/process/behind-the-design-adobe-content-authenticity-app>

And the C2PA itself provides an entire document concerning User Experience Guidance at <https://c2pa.org/specifications/specifications/2.0/ux/UX_Recommendations.html>, which has been developed from a variety of user research projects over the years. 

**8. Provide any research or evidence supporting the effectiveness of your tool.**

User research is described in Q7.

A quote from the BBC research:

We were encouraged by a self-selecting, limited audience trial of 1,200 people who answered three multiple choice questions. Their answers suggested that:

- 83% trust the media more after seeing our Content Credentials

- 96% found our Content Credentials useful

- 96% of users say they found our Content Credentials informative

We conducted our tests based on three different types of images: editorial, stock image, and user-generated content (UGC). Adding provenance information served as an equaliser of trust across the image types, with them all eliciting the same levels of trust. Where no provenance information is shown, UGC had the highest levels, followed by stock images and then editorial images.

**9. What aspects of your proposal would benefit from being standardized? With which systems does it need to interoperate? How will this fit into existing technical and social systems (e.g. browser extension, peer review)?**

See the various specifications listed under Q1. The eventual goal of C2PA is to have provenance metadata produced, maintained, and signed throughout the production process, from camera through newsroom workflow systems, to publishing tools and distribution platforms. This requires all publisher tools, platforms and consumer tools such as web browsers to handle C2PA signatures and metadata.

**10. Create a threat model for your proposal. Are there potential unintended consequences, such as enabling censorship or increasing bias? What are potential attack vectors? What can be done to mitigate these risks?**

The [C2PA Harms Modelling](https://c2pa.org/specifications/specifications/1.0/security/Harms_Modelling.html) document describes a methodology, but does not include a description of actual harms and mitigations. These are listed in the [Harms, Misuse and Abuse Assessment](https://c2pa.org/specifications/specifications/1.0/security/_attachments/Due_Diligence_Actions.pdf). [C2PA Security Considerations](https://c2pa.org/specifications/specifications/1.0/security/Security_Considerations.html#_threats) also lists some specific threats. 

**11. What do you hope for from W3C in this effort?**

- Recommendations for how we can work towards getting C2PA, IPTC and other trust lists supported by the Web Platform. Ideal would be support in browsers, similar to the HTTP “padlock” icon in the location bar

* Help us work towards a standardised API that covers how C2PA signals can be exposed as part of the Web Platform

* Help in evangelising our work and the benefits of signing content

* Understanding any reservations around the specifications and policies, specifically from a Web Platform perspective, and hopefully aligning on our intent to help build a more authentic media ecosystem 