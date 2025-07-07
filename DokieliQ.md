# Authentic Web Workshop Questionnare: Dokieli

Answer these questions using your familiarity with __<a href="https://www.w3.org/2018/10/credibility-tech/">Technological Approaches to Improving Credibility Assessment on the Web</a>__ (Section 4). Consider your tool as a link in the credible web ecosystem. 

## 1. Logistics. Provide a brief description of your technology, tool, or proposal. How can we contact you? In what time zone are you located? Please link to Github repos, proposals, explainers, or drafts that you’ve written.

Dokieli is a client-side editor and browser extension for decentralised article publishing, annotations, and social interactions, built as an open-source project using open web standards. Dokieli's core design principles are autonomy and universal access.

dokieli enables individuals and communities, to share, publish, and annotate articles using their preferred identities and storage, all under their control. All content produced by dokieli can be used with other standard-compliant applications, so you are always free to switch to another application and take your content with you.

Contact:

* Website: https://dokie.li/
* Source code: https://git.dokie.li/
* Social media: https://w3c.social/@dokieli
* Contact: [Sarven Capadisli](https://csarven.ca/#i) ( info@csarven.ca ) , [Virginia Balseiro](https://virginiabalseiro.com/#me) ( info@virginiabalseiro.com )
* Time zone: Central European
* See also:
  * [Decentralised annotations and activities in dokieli](https://lists.w3.org/Archives/Public/public-solid/2024Nov/0004.html) - using W3C specifications, how articles and annotations can be published and shared in a fully decentralized manner, creating a social layer on top of the document layer.
  * [Dokieli y Fundación Cibervoluntarios unidos en la creación de una herramienta que permite a la ciudadanía un uso reflexivo de la información y el control de sus datos](https://www.cibervoluntarios.org/es/actualidad/post/dokieli-y-fundacion-cibervoluntarios-unidos-en-la-creacion-de-una-herramienta-que-permite-a-la-ciudadania-un-uso-reflexivo-de-la-informacion-y-el-control-de-sus-datos) - Partnership announcement with Fundacion Cibervoluntarios
  * [w3c.social/@dokieli overview thread](https://w3c.social/@dokieli/114660264397190587)

## 2. What problem(s) are you trying to solve? What use cases are you addressing? How do you define credibility? Describe the actors involved.

### Problems

Since the web platform lacks built-in authenticity and credibility assessment methods, there is no native way to trace claims back to their sources for provenance. Our goal is to equip individuals with tools to critically engage with content, using contextual insights to assess credibility by highlighting gaps, providing supplemental data, and incorporating annotations.

Some of the problems we are looking to help solve include:

* Information overload, inefficiency, uninformed decision-making or lack of meaningful context.
* Echo chambers, misinformation, and disinformation.
* Centralization, surveillance, and tracking.
* Control/ownership of content and identity.

### Use Cases

#### Readers

* As a reader of online content, I want to see contextual credibility indicators while browsing articles in order to assess the trustworthiness of the information.

#### Creators

* As a fact-checker, e.g., journalist, activist, I need to annotate and share fact-checked insights on web content in order to provide transparency and counter misinformation.
* As a student or researcher, I want to highlight, organize, and reference credible sources directly within online content in order to streamline my research process.
* As a content creator, I want to produce content for public consumption, and assess and process information sources to maintain their credibility.

#### Disseminators

* As a teacher or trainer, I want to make sure that the information I distribute is credible and trustworthy.

### Credibility

Credibility assessment is performed by individuals or communities using dokieli's indicators, rather than by dokieli itself. This design is intentional, aiming to build digital literacy so people develop the ability to assess content independently. The goal is to encourage habits and patterns that support critical thinking when the tool is unavailable.

For dokieli, credibility is an assembly of indicators based on content analysis and knowledge extraction, content validation, fact-checking through annotations from domain experts and social circles, media bias and source evaluation, presentation of evidence, and alignment with an individual's preferences such as their profile, policies, interests, principles, and filters.

## 3. Explain the chain of events that help assess credibility in your proposal. What architectural choices have you made that enable this?

Dokieli can be embedded into any HTML document, a standalone web application, or a browser extension, offering full functionality directly in the browser.

The following features are helpful both to readers engaging with content on the web, as well as to writers when they are producing content.

1. User Requests Insights
  1.1. The user selects "Insights" from the menu to analyze the entire document.
  1.2. Alternatively, the user highlights a portion of text and selects "Insights", triggering a query to public data sources (such as Wikidata) for relevant information.
2. Content analysis and knowledge extraction: The system identifies topics, detects sentiment, and applies content warnings if necessary.
3. Content validation: The system evaluates the text for missing citations, unsupported arguments, or manipulative rhetoric. If applicable, it assesses media bias, public knowledge, and source credibility.
4. Fact-Checking and evidence: Relevant annotations, trusted sources and authoritative data are retrieved to support or challenge claims in the text.
5. User receives Insights: The system presents key findings and suggestions to improve credibility, along with source links and references.

See also question 6.

Our goal is to build on these foundations and other work to further develop the features on assessing credibility on the web. We are also aware of gaps in standardisation as well as obtaining relevant data to meet the use cases.

## 4. Which role(s) does your proposal fill in the ecosystem (noting that some tools fill multiple roles):

* Content Consumer - Person receiving the information (audience, reader)
* Content Provider/Source - Person(s) or organizations delivering content
* Content Promoter - Person(s) or organization that amplify the spread of information
* Credibility Facilitator - Person(s) or organization who is helping the consumer decide what to trust.
* Platform - Technological system, and by extension the person or organization who maintains and controls it.

## 5. Which <a href="https://www.w3.org/2018/10/credibility-tech/#h.32pkwj5grlt3">technical approaches</a> do you enable? Are there other ecosystem players that enable the technical approaches with which you will interoperate? Please elaborate

* Inspection: Web Annotations with various motivations and purposes, e.g., assessing, bookmarking, classifying, commenting, describing, highlighting, linking, replying, questioning, tagging, can be made (implemented), and they can be discovered through Notifications. There is also various metadata available from annotations and notifications, e.g., attribution, date, license. There are also typed citations, e.g., refutes, extends, cites for information, cites as authority.
* Corroboration: Notifications to contacts or community inboxes expressing a request for claim verification with a note. Web Annotations with "fact-check" motivation.
* Reputation: Web Annotations using personal storages and social graph and providing provenance data.
* Transparency: Allowing labeling of information, aggregating and analyzing machine-readable disclosures.

We need to explore how community-controlled fact-checking can be carried out with appropriate moderation, incorporating domain expertise or reputation, factoring in anonymity, and other challenges, e.g., [Addressing social implications of annotations and UX](https://github.com/dokieli/dokieli/issues/152), [Annotation motivations](https://github.com/dokieli/dokieli/issues/146).

## 6. Describe how your technology, tool, or proposal works from a technical perspective.

dokieli enables individuals and communities, to share, publish, and annotate articles using their preferred identities and storage, all under their control. All content produced by dokieli can be used with other standard-compliant applications, so individuals are always free to switch to another application and take their content with them.

The Contextual Insights features will be implemented as a web browser extension that can be triggered on any webpage to provide a credibility assessment. For the core content analysis features, in order not to rely on external services, we will consider clientside libraries and develop our own where necessary to maintain control over ethical principles, sustainability, and privacy. If external services prove to be effective and align with these values, they may be integrated, provided they meet strict data-handling standards and include mechanisms for informed user consent.

Dokieli implements:

* [Linked Data Platform](http://www.w3.org/TR/ldp/), [Solid Protocol](https://solidproject.org/ED/protocol) - to discover interactions from the user's storage
* [Linked Data Notifications](https://www.w3.org/TR/ldn/) - to discover a document's inbox and notifications.
* [Web Annotation Protocol](https://www.w3.org/TR/annotation-protocol/) - to discover annotation services and collections of annotations.
* [Web Annotation Vocabulary](https://www.w3.org/TR/annotation-vocab/) - to use applicable annotations that are associated with a document or its parts.
* [ActivityPub](https://www.w3.org/TR/activitypub/) - to send activities and discover interactions from the user's and their contact's outbox.
* [ActivityStreams](https://www.w3.org/TR/activitystreams-vocabulary) - to use relevant activities and identify users.
* [WebID](https://www.w3.org/2005/Incubator/webid/spec/identity/) - to identify users and access their profile information, including preferences.
* [Solid Type Indexes](https://solid.github.io/type-indexes/) - to locate specific resource types for both the user and their contacts.
* [Web Access Control](https://solidproject.org/TR/wac) - to set authorization rules on resources for different agents.
* [ODRL Information Model](https://www.w3.org/TR/odrl-model/) - to examine information about the storage (location, name, description, owners, URI persistence policy, and digital rights policies).
* [Memento](https://tools.ietf.org/html/rfc7089) - to access the memento (version history) of a document.
* [Robust Links](http://robustlinks.mementoweb.org/) - to help mitigate content drift and link rot, links can be enhanced with additional context.
* [SPARQL Query Language](https://www.w3.org/TR/sparql11-query/) - to query structured data from public.
* [SPAR Ontologies](http://www.sparontologies.net/) - to create and consume fine-grained (e.g., sentence-level) typed citations.
* [PROV: The PROV Ontology](https://www.w3.org/TR/prov-o/) - to provide provenance activity about the performed statistical data analysis.
* ...

## 7. Describe the user experience and the user research that went into development.

We are collaborating with Fundacion Cibervoluntarios ( https://www.cibervoluntarios.org/ ) to conduct user research, which will be focused on how users engage with online content and their understanding of decentralization and related technologies. We aim to assess how well the features that we're planning to implement can aid them in engaging with content more critically, while respecting their autonomy.

This research includes focus groups with target groups, as well as an online survey. See also an announcement on the credibility CG mailing list: [Survey on assessing online credibility and decentralization technologies](https://lists.w3.org/Archives/Public/public-credibility/2025Jun/0002.html)

More generally on the background of the tool:

* [Decentralised Authoring, Annotations and Notifications for a Read-Write Web with dokieli](https://csarven.ca/dokieli-rww) - peer-reviewed academic paper, 2017
* [Linked Data Notifications: a resource-centric communication protocol](https://csarven.ca/linked-data-notifications) - peer-reviewed academic paper, 2017

## 8. Provide any research or evidence supporting the effectiveness of your tool.

The effectiveness of this tool will be assessed through planned pilot programs, in collaboration with Fundacion Cibervoluntarios. These will evaluate whether decentralization enhances the resilience of information ecosystems, and whether dokieli's features are effective in helping users assess the credibility of a statement or document. Findings will be used to refine the features and inform best practices. See also: https://www.cibervoluntarios.org/es/actualidad/post/dokieli-y-fundacion-cibervoluntarios-unidos-en-la-creacion-de-una-herramienta-que-permite-a-la-ciudadania-un-uso-reflexivo-de-la-informacion-y-el-control-de-sus-datos

## 9. What aspects of your proposal would benefit from being standardized? With which systems does it need to interoperate? How will this fit into existing technical and social systems (e.g. browser extension, peer review)?

Dokieli is already a browser extension, and includes features to allow different users to review as well as other social interactions. Reviews (annotations with different motivations) can be stored at different locations on the web.

See also question 11.

## 10. Create a threat model for your technology, tool, or proposal. Are there potential unintended consequences, such as enabling censorship or increasing bias? What are potential attack vectors? What can be done to mitigate these risks?

In progress. Some potential concerns that we have identified:

* Moderation
* Preventing harassment
* Manipulation of the fact-checking features by bad actors
* Selection or curation of data sources
* Reliable way to identify biases

## 11. What do you hope for from W3C in this effort?

* A standardised Credibility Assessment Data Model
* Development of an Argumentation Data Model
* Development or extension of Web Annotation motivations
* An authentication mechanism better suited to browser extensions that supports user-controlled identity
