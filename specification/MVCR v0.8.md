# Record of Consent - Minimum Viable Consent Receipt #

| Document Information  | |
| ------	| ------	|
| Version: | 1.0 Draft 0.8 |
| Date: | March 6, 2016 |
| Editors: | Mark Lizar |
| | Heather Flanagan |
| Contributors: |	Iain Henderson |
| |	Mary Hodder |
| |	Justin Richer |
| |	Sarah Squire |
| |	John Wunderlich |

# Abstract

The Consent & Information Sharing Working Group (CISWG) is specifying a set of requirements to create a minimum viable consent receipt that can be used to document consent transactions for an open ended set of consent contexts. This specification identifies the common consent requirements to record a personal data transaction and provides a reference for conformance to various uses of the MVCR specification.  

The objective is to address existing closed consent architecture with a consent record standard which provides a foundation for an open consent architecture.  Addressing multiple privacy principle requirements and providing a by doing so providing a framework for operationally addressing multiple Fair Information Practice Principles and likewise ISO 29100 principles.
(editors note: reference FIPP properly )

In addition to (ISO Principles - "Openness, transparency, notice") and Consent (ISO Principle 1 - "Consent and Choice") are fundamental privacy principles, addressed with this specification.


# Status of this document

The v0.8 draft is a specification candidate - this draft version is for peer review and not meant for distribution.

## Copyright Notice

Copyright (c) 2016 Kantara and the persons identified as the document authors. All rights reserved.

This document is subject to the [Kantara IPR Policy - Option Patent & Copyright: Reciprocal Royalty Free with Opt-Out to Reasonable and Non-discriminatory (RAND)](https://kantarainitiative.org/confluence/download/attachments/2293776/Kantara%20Initiative%20IPR%20Policies%20_V1.1_.pdf?version=1&modificationDate=1244488630000&api=v2)[HTML version](https://kantarainitiative.org/confluence/pages/viewpage.action?pageId=41025689)

## 1.	Introduction
The Minimum Viable Consent Receipt (MVCR) is a specification for describing common requirements for consent in and across jurisdictions for a variety of consent contexts.

### 1.2 Scope
This Minimum Viable Consent Receipt  specification has the scope of specifying a receipt for recording the provision of consent. This scope includes how a consent record is provided, how to present the record, the timing of the record, the format and order of fields and what data should be in the fields, linking the records of the fields to policy documents, icons, along with guidance for adding additional elements.

### 1.3 Scope definition
The term 'minimum' in the MVCR refers to the least amount of information to make a consent receipt viable for a number of different context that is defined by the Data Controller (or grantor).  From the minimum open consent record with the least amount of fields possible for the record to be independently usable by both parties, for a consent record for non explicit consent, for an explicit machine readable consent receipt, to an explicit machine readable consent with explicitly specifying sharing of consent.  
 Viable, in this scope, means a record of consent that can be retained and used separately by both issuer (grantor) and recipient (grantee).

 ** omit? ** The consent receipt (SHOULD/MUST) in all contexts involve the minimal set of notice requirements for the company or organization issuing the receipt to provide proof of consent. **

The receipt has two modes explicit consent or non-explicit consent specified with a yes/no flag, for numerous reasons. The primary reason of these modes is to facilitate high level of interoperability/extensibility with various; a) consent contexts across different mediums, b) simple legacy consent requirements to complex privacy compliance requirements, c) for adoption with or without legal liability,  d) so that the receipt is a consent record that is machine readable. e) Explicit consent is defined by regulation and up for little or no interpretation.

* Yes, indicating the receipt shows compliance and conformance for explicit consent.
* No, indicating the receipt has demonstrated conformance with the MVCR and demonstrates, but is a limited to, conformance and makes no legal compliance claims.   

Both operational modes demonstrate at a minimum, open consent conformance to the MVCR.  Providing flexibility for implementation and adoption without the burden of legal compliance obligations for the implementor. (see conformance table)


### 1.4 Notational Conventions for Conformance

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC 2119](http://www.rfc-editor.org/info/rfc2119).

 [RFC7159](https://docs.kantarainitiative.org/uma/rec-uma-core.html#RFC7159) data structures defined by this specification MAY contain extension properties that are not defined in this specification. Any entity receiving or retrieving a JSON data structure SHOULD ignore extension properties it is unable to understand. Extension names that are unprotected from collisions are outside the scope of this specification.

### 1.5 Terminology ###

Much of the basic terminology herein is from [ISO/IEC 29100:2011 "Information Technology -- Security techniques -- Privacy Framework"](http://standards.iso.org/ittf/PubliclyAvailableStandards/c045123_ISO_IEC_29100_2011.zip).

>> ISO/IEC 29100:2011 ...provides a privacy framework which
>>
>> * specifies a common privacy terminology;
>> * defines the actors and their roles in processing personally identifiable information (PII);
>> * describes privacy safeguarding considerations; and
>> * provides references to known privacy principles for information technology.
>>
ISO/IEC 29100:2011 is applicable to natural persons and organizations involved in specifying, procuring, architecting, designing, developing, testing, maintaining, administering, and operating information and communication technology systems or services where privacy controls are required for the processing of PII."

The following are terms that are not referenced in 29100 and are used or referenced in this standard:


* **Consent & Information Sharing Work Group (CISWG)**
	The [Kantara Initiative](https://kantarainitiative.org/) Work Group responsible for this standard.

(note: we need to include the terms we use in the spec, not just reference them)

* **Consent Receipt (CR)**
	A record of a personal information consent transaction.

* **Consent Receipt Generator (CRG)**
	A demonstration API that instantiates the MVCR.

* **Data Subject (DS)**
	See PII Subject in in ISO/IEC 29100:2011

  **Explicit Consent**

* **Individual**
	see PII Subject in ISO/IEC 29100:2011.

* **Information Sharing**
	A statement or series of statements that set out what information is shared with third parties and for what purpose(s).

* **Minimum Viable Consent Receipt (MVCR)**
	This standard

  **Notice**

* **Personal Information (PI)**
	See Personally Identifiable Information (PII) in ISO/IEC 29100:2011

* **Purpose Specification**
	A statement or series of statements that set out the purpose(s) for which PII has been collected.

* **Sensitive Personal Information Categories**
	All sensitive categories require explicit consent.
  Some jurisdictions call out categories of PII that, by virtue of their sensitivity, require higher levels of protection. The particular categories vary by jurisdiction but will typically include health data (or personal health information - PHI), financial data, political affiliations and similar categories.

## 2. Core MVCR Profile
The MVCR is broken down into 5 sections for usability and to aid in understanding the core function. The 5 sections are:

1.	Header
2.	PII Controller, Contact & Policy
3.	Purpose(s)
4.	Personally Identifiable Information
5.	Information Sharing

The order is specific and is part of the specification.

### 2.1 Header

The purpose of this section is to set out the meta-data for the consent transaction. This section will contain the following fields:

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Receipt Field Description | Purpose of Field  |
| --- | --- | --- | --- |
| Explicit Consent (y/n)  | Yes or No | explicit_consent |
| Jurisdiction | The legal jurisdiction that the PII controller will apply to this collection of PII | Required | Typically should be an ISO two letter country code |
| Consent Time Stamp | The time and date that the consent receipt was issued | Required | Date and time including time zone, or in UTC |
| Consent Type | Implied or Expressed Consent (or N/A in the case where collection is a legal requirement) | Required | **Note 1:** If collection is required by law, consent should not be sought except for other purposes, since consent is only meaningful if the PII Subject may say no. **Note 2:** If the PII is sensitive (below) and consent is required for collection, expressed consent will be required in many jurisdictions |
| Collection Method | A description of how the consent was collected | Optional | Describe the type and method collection method such as "Implied by completion of web form" or "Expressed with opt-in check box". |
| Collection Site | Identify the location where the collection occurred | Required | Typically a URI such as http://www.consentreceipt.org for web transactions. |
| Consent ID | A unique identifier for the consent receipt | Required | A globally unique ID (GUID) |
| PII Subject | An identifier or token for the natural person whose information has been collected and who has given consent | Required | John Doe |

#### Header Example

| Field | Contents|
| ------:	| ------	|
| __Jurisdiction:__ | CA |
| __Consent Time Stamp:__ | 2016/02/08 12:20:34 EST |
| __Consent Type:__ | Expressed |
| __Collection Method:__ | Opt-In checkbox on a web form |
| __Collection Site:__ | [http://www.consentreceipt.org](http://www.consentreceipt.org) |
| __Consent ID:__ | C159A448-A69B-44BF-BFCE-6403FB5D06EE |
| __PII Subject_Identifier:__ | [roadrunner@fictional.url](mailto:roadrunner@fictional.url) |


### 2.2 PII Controller, Contact & Policy

The purpose of this section is to identify the entity that is accountable for data protection and the privacy policy tp which the consent is bound.

| Field Name | Description | Type | Notes |
| --- | --- | --- | --- |
| Data Controller | That entity that is accountable for compliance over the PII | Required | Typically the entity that owns the web site that the is issuing the consent receipt |
| Data Processor | The entity that has collected the PII | Optional | When the site operator is acting on behalf of the Data Controller |
| Contact Name| The person/role to contact for privacy issues | Required | |
| Contact Address | Physical Address | Required | |
| Contact Email | Email Address | Required | |
| Contact Phone | Phone Number | Required | |
| Privacy Policy | URL of the privacy policy as at the time of the receipt | Required | Note that this means that the entity needs to retain copies of prior privacy policies |
| Privacy Label | URL of the short privacy notice, if one exists for the entity | Optional | This field is still only tentatively part of the standard |

#### PII Controller, Contact and Policy Example ####

| Field | Contents|
| ------:	| ------	|
| __Data Controller:__ | Acme Corporation, Inc |
| __Data Processor:__ | null |
| __Contact Name:__ | Mel Blanc |
| __Contact Address:__ | 123 Main Street, Somewhere Else |
| __Contact Email:__ | [mel.blanc@fictional.url](mel.blanc@fictional.url) |
| __Contact Phone:__ | +1 555 555-1212 |
| __Privacy Policy:__ | [ACME Privacy Policy](https://www.acme.fictional.url/privacy.policy) |
| __Privacy Label:__ | [ACME Privacy Label](https://www.acme.fictional.url/privacy.label ) |

### 2.3 Purpose(s)

The purpose of this section is to identify the primary purpose(s) for which the PII Controller is collecting PII, along with any secondary purposes for which the PII might be collected.

| Field Name | Description | Type | Notes |
| --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the purpose(s) for collection |
| Service | Site, app, or service | Required | Name of the site, the app or the service that will use the PII collected |
| Purpose | Description of purpose | Required | Should be explicit and specific as reasonably necessary to fulfill the Service |
| Primary | Is this the primary purpose for collecting PII? (True|False) | Required | Typically only one purpose should be identified as primary. |
| Necessary | Is this a necessary purpose? (True|False) | Required | The primary purpose will be necessary, but may not be the only necessary purpose. PII subject should be able to provide consent directives to opt out of purposes not identified as necessary . |

#### Notes on Purpose(s)

* Each purpose MUST link the service name to at least one explicit and specific purpose.
* Each purpose SHOULD contain an external reference to an on and off preference for this purpose.
* Each purpose MAY contain additional options. Some examples include a trust mark icon or link, a data retention specification, or a link to the purpose description in the policy.

**Note:** A list of commonly used purposes is provided in Appendix B below.
**Note:** Managing consent directives is out of scope of the MVCR.

#### Purpose Specification Example ####

| Service | Purpose | Primary | Necessary |
| ------ | ------ | :------: | :------: |
| __Acme Web Site__ | Core Function | True | True |
| __Acme Web Site__ | Contact Requested | False | False |
| __Acme Web Site__ | Personalized Experience | False | False |
| __Telling PII Subject about other services__ | Marketing | False | False |
| __Telling PII Subject about third party services__ | Marketing Third Parties | False | False |

### 2.4 Personally Identifiable Information

The purpose of this section is to ensure that the PII Subject is made aware of the types of PII that has been collected and may be used or disclosed.

| Field Name | Description | Type | Notes |
| --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the types of PII |
| Category | Label for a type of data that may be collected | Required |  |
| PII | Short description of the category | Required |  |
| Sensitive | Whether or not this type of data is _Sensitive PII_ in the PII Controller's jurisdiction | Required |  |
| Notes | Discretionary field to explain why (or why not) PII is sensitive | Optional |  |

#### PII Example ####

The example below is for an on-line pharmacy that provides a delivery service

| Category | Description | Sensitive | Explanation |
| ------ | ------ | :------: | :------: |
| __Browser Data__ | Information revealed by the browser to the web server | False | IP address is PII but not sensitive |
| __Address__ | Physical address for deliveries | False | |
| __Health__ | Personal Health Information| True | Specified by regulation in many jurisdictions |
| __Financial__ | Credit Card or payment information | True | Specified by regulation in many jurisdictions |


### 2.5 Information Sharing

The purpose of this section is to provide the PII Subject with information about how their information is shared with third parties. In the MVCR this is a Y/N (binary on and off) flag, and if On, then the 3rd parties, the specified purpose and at the minimum the data categories shared may be listed here.

| Field Name | Description | Type | Notes |
| --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary identify third parties |
| Sharing | Category(ies) of data shared | Required |  |
| Third Party | Third party that receives the data | Required | SHOULD be specific, MAY be generic |
| Purpose | Purpose (only from list above) for sharing data | Required | **Note:** PII provided to vendors or suppliers to the PII Controller that are providing data processing services of PII to the PII Controller would not normally be considered disclosure or information sharing |

#### Information Sharing Example

The following example is from an online financial institution

| Sharing | Third Party | Purpose | Explanation |
| ------ | ------ | :------: | :------: |
| __Financial__ | Tax Authority  | Required by Law Enforcement or Government | Financial institution required to disclose personal financial information for tax purposes |
| __Contact__ | Advertising Network| Marketing Third Parties | Ad supported web site |

# 3. Fields in Review v0.8:

In order to create v0.7 much has been cut to the minimum, this includes some feild that are in review, these are

 * Review consent transaction data
 * Review consent context
 * Review consent payload
 * Review Resource Server Identifier
 * Review OAuth Scopes
 * Review and what is —> Audience URI
 * Consent Location

# 4. Appendices

## 4.1. Appendix A: JSON example

A demonstration version of the MVCR can be found on the [Example Consent Receipt Generator (CRG)](https://mvcr.herokuapp.com/) page. The example site also contains [API documentation](https://mvcr.herokuapp.com/doc/). This server contains a consent receipt generation API. The API consists of a single endpoint at [http://www.consentreceipt.org/mvcr/api](http://www.consentreceipt.org/mvcr/api). This endpoint accepts HTTP POST requests with input in the form of JSON (application/json) documents and returns output in the form of a signed JSON Web Token (application/jwt). The example site consists of two pages:

* The Consent Receipt Generator Input Example and Receipt Rendering page at which users can experiment with inputs and see the corresponding output. This may be used to help develop implementations and see how the consent receipt code is working. The code for this page can be found at [https://github.com/bspk/cr_web](https://github.com/bspk/cr_web).

* A page for API Documentation and examples at [http://api.consentreceipt.org/doc/](http://api.consentreceipt.org/doc/)

The API takes in a JSON document describing the consent transaction for which the receipt is to be generated. This object includes artifacts such as the presiding jurisdiction for the consent action, an identifier for the party consenting. The output of the API is a signed JSON Web Token (JWT) whose payload consists of all of the input data as well as several additional fields. The output JWT is signed by the server using the RS256 algorithm defined in JSON Web Signatures. The server's public key is published in JSON Web Key format at: http://www.consentreceipt.org/api


### JSON Proporties

The JSON object described above has the following properties. (You may also see the definition of the MVCR fields above):

1. The receipt MUST have a property to authenticate the origin.
2. The receipt MUST have an integrity protection property.
3. The audience SHOULD be restricted and transparent.
4. The receipt SHOULD be able to be transmitted over various transport protocols.
5. The payload MUST have a human readable section, and SHOULD have a machine readable section.
6. The payload SHOULD include the following properties:
 a) Issuer
 b) Date
 c) Time
 d) direct contact information to data controller
 e) Contain a static Link to privacy policy
 f) Purpose (s)
 g) YES or NO Flags
 * 3rd party data sharing
 * Sensitive Personal Data Collection
 * Operational Context
7. The payload SHOULD include the following properties:
 a) A description of the types of personally identifiable information to which the consent applies.
8. The payload SHOULD include the following information:
 a) the personal identifier used in the consent receipt
 b) some or all of the personally identifiable information to which the consent applies
8. The receipt MUST be systematically usable and automatically discoverable
9. Receipts MUST contain the minimum information to enable request for more information, if required
10. Receipts MUST contain the minimum information to enable requests for more information, if required

### JSON Field Table

The following table sets out the fields contained in a JWT that meets the information requirements for a Minimum Viable Consent Receipt.

| Field Name | Data Type | Description | Example Input |
| :---: | --- | --- | --- |
| Section 1: CR Header | | This is the first section of the receipt | |
| jurisdiction | string. ISO two-letter country code if applicable, otherwise free text | This is the jurisdiction that governs the PII Controller | US |
| iat | number. Integer number of seconds since 1970-01-01 00:00:00 GMT | Timestamp of when the consent was issued | 1435367226 |
| moc | Method of collection | Is used to describe how the consent was collected i.e. webform opt in, or implicit, verbal, etc. | web form |
| iss | string. HTTPS URL | This is the URI or Internet location of processing, i.e., one party-two party or three | http://www.consentreceipt.org/ |
| jti | string | Unique identifier for this consent receipt | 9ef6b81a414b2432ec6e3d384c5a36ce-a8aa0c30d3dd2b67364126ed80856f9c-20654f032eef87ad981187da8c23c118-6eefe1503714835c2e952bbb3f22729c |
| sub | string | PII Subject provided identifier, such as an email address, user ID or a claim, defined with a namespace | example@example.com |
| Section 2: PII Controller | | This section has the PII Controller, contact and privacy service information | |
| data_controller | object | The identity and company of the PII controller and any party delegated to be a PII processor on behalf of the PII controller | {"on_behalf": true, "contact": "Dave Controller", "company": "Data Controller Inc.", "address": "123 St., Place", "email": "dave@datacontroller.com", "phone": "00-123-341-2351"} |
| Section 2: data controller object fields | | | |
| on_behalf | boolean | acting on behalf of an organization? | TRUE |
| contact | string | Person to contact | Jon Doe |
| company | string | Company name | Data Controller Inc. |
| address | string | Physical address | 123 Main St., Anywhere |
| email | string | Contact email address | jon@datacontroller.com |
| phone | string | Contact phone number | 00-000-000-0000 |
| end of object fieds | | | |
| policy_uri | string HTTP URL | The internet and immediately accessible privacy policy of the service referred to by the receipt | http://www.example.com/privacy |
| Section 3: Purpose Specification| | List Purposes| |
| purpose | array of string's arrays| Explicit, Specific and Legitimate: interpreted here as: 'Naming the Service' and 'Stating the Active Purpose ' see Appendix B for these requirements| [Bob’s store, delivery, ]or [[" CISWG Membership", "Join"]] |
| Section 4: Sensitive Personal Information | | Identify sensitive PII | |
| sensitive | array of strings | In many jurisdictions their are additional notice and administrative requirements for the collection, storage and processing of what are called Sensitive Personal Information Categories. These are Sensitive in the business, legal, and technical sense, but not specifically in the personal context. This list of categories are required in some jurisdiction, but, the actual notice and purpose requirements are out the scope of the MVCR. | ["health"] |
| Section 5: Information Sharing | | Sharing information with 3rd parties, what categories, with whom, and how information is shared | |
| sharing | object | | |
| Section 5 object fields | | | |
| sharing| array of strings| Data categories to share | None |
| party_name | string | 3rd party to share data | 3rd Partry name or 3rd Party Category | |
| purpose| string | How information is shared | None |
| Section 6: Optional or In Review | | | |
| notice | string. HTTP URL | Link to the short notice enables usability and layered policy. to provide enhanced transparency about data collection and information sharing practices | [http://example.com/shortnotice](http://example.com/shortnotice) |
| scopes | string. space seperated string values | What you’re allowed to do on the service (these can be tied to legal / business / technical layers) | read update |

**Note:** Table incomplete. See [https://mvcr.herokuapp.com/doc/](https://mvcr.herokuapp.com/doc/)

## 4.2. Appendix B: Purpose List

The list below contains a list of purposes for which Personally Identifiable Information (PII) has been collected, based on input from subject matter experts. This list is neither normative, in that none of these are required purposes in any given context, nor complete, in that each purpose for each collection by each entity is contextually specific. This list is provided for convenience and demonstration purposes. It is the case that in many jurisdictions, the entity collecting PII for identified primary purposes may not use that same information without the consent of the PII Subject for secondary purposes, unless required to do so by law, and it is the case that the PII Subject should be able to deny consent for secondary purposes while still receiving core functions from the site, application or service.

| # | Description | Short Code | Notes |
| --- | --- | --- | --- |
| 1. | To enable the entity to carry out the core functions of its site/app/services. | _Core Function_ | Default Purpose |
| 2. | To provide contracted or requested services to the PII Subject. | _Contracted Service_ | |
| 3. | To deliver contracted or requested services to the PII Subject. | _Delivery_ | |
| 4. | Communicating with you about information or services you specifically request. | _Contact Requested_ | |
| 5. | Providing you with a personalised experience of our site/app/service. | _Personalized Experience_ | |
| 6. | Communicating with you about our other services you may be interested in. | _Marketing_ | |
| 7. | Communicating with you about the services of third parties you may be interested in. | _Marketing Third Parties_ | |
| 8. | Providing the information to third parties to deliver our services on our behalf. | _Sharing for Delivery_ | |
| 9. | Providing the information to third parties to enable them to communicate with you about their own services you may be interested in. | _Sharing for Marketing_ | |
| 10. | Providing the information to third parties to enable them to deliver or improve their own services to you. | _3rd Party Sharing for Core Function_ | |
| 11. | Providing the information to third parties to enable them to deliver or improve their own services to others. | _3rd Party Sharing for ..._ | |
| 12. | Complying with our legal obligations for record keeping. | _Legally Required Data Retention_ | |
| 13. | Complying with our legal obligations to provide the information to law enforcement or other regulatory/government bodies. | _Required by Law Enforcement or Government_ | |
| 14. | Protecting your vital and health interests. | _Protecting Your Health_ | |
| 15. | Protecting our legitimate interests, yours or those of a third party. | _Protecting Our Interests_ | |
| 16. | Measure or improve our performance or the delivery of our services. | _Improve Performance_ | |

Other purposes may be uses as appropriate for the specific context of each jurisdiction and the site, application or service.

## 4.3. Appendix C: Categories of Personal Data (explainers/examples)

- 1.	Biographical – (General information like Name, DOB, Family info (mother’s maiden name), marital status. Historical data like educational achievement, general employment history.)
- 2.	Contact – (Address, Email, Telephone Number, etc.)
- 3.	Biometric – (Photos, fingerprints, DNA. General physical characteristics – height, weight, hair colour. Racial/ethnic origin or identification - whether self-identified or not)
- 4.	Communications/Social – (Email, message and phone records – both content and metadata. Friends and contacts data.)
- 5.	Network/Service – (Login ids, usernames, passwords, server log data, IP addresses, cookie-type identifiers)
- 6.	Health – (Ailments, treatments, family doctor info. X-rays and other medical scan data)
- 7.	Financial – (This includes information such as bank account, credit card data. Income and tax records, financial assets/liabilities, purchase/sale of assets history.)
- 8.	Official/Government Identifiers – (This includes any widely recognised identifiers that link to individual people. Examples include National Insurance, ID card, Social security, passport and driving licence numbers, NHS number (UK). Just the numbers rather than data associated with them.)
- 9.	Social Services/Welfare – (Welfare and benefits status and history)
- 10.	Judicial – (Criminal and police records, inc. traffic offenses.)
- 11.	Property/Asset – (Identifiers of property – licence plate numbers, MAC addresses for mobiles, other device identifiers. Not financial assets. Could include digital assets like ebook and digital music data)
- 12.	Human Resources – (Records held about employees/ members/ students not elsewhere defined. Incl. HR records such as job title, attendance/disciplinary records. Salary - as opposed to income.)
- 13.	Psychological/Attitudinal – (Inc. religious, political beliefs, sexual orientation and gender identity – though not genetic gender which is Biometric. Traits and personality measures or assessments, but not psychological health - which is health data).
- 14.	Membership – (Political, trade union affiliations, any other opt-in organisational/group membership data - third party organisations only. Includes name of employer when not held by employer. Could extend to online platform membership. Some might be more sensitive than others – may want a separate category)
- 15.	Behavioural – (Any data about the behaviour, habits or movements of an individual - electronic or physical. Location, browser/search history, web page usage (analytics), energy usage (smart meters), login history, calendar data, etc.)
- 16.	Profile – (Marketing and social segmentation data. Any categorisation that impacts information presented or decisions made about an individual. This might be observed or derived data (algorithmic) or volunteered by the individual. Profile data is often generated from Behavioural data).
