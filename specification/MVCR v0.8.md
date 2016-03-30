# Record of Consent - Minimum Viable Consent Receipt (MVCR) #

| Document Information  | |
| ------	| ------	|
| Version: | 1.0 Draft 0.8 |
| Date: | March 6, 2016 |
| Editors: | Mark Lizar |
| Contributors: |
| |	John Wunderlich |
| |     Justin Richer   |
| |     Mary Hodder     |
| |     Iain Henderson  |
| |     Sarah Squire    |


# Abstract

This specification identifies the common consent requirements to record a personal information (PI) sharing transaction and provide this record as an independent receipt.

The MVCR is designed to address existing closed consent architecture,  by providing a specification for creating a consistent record of consent.    The common consent format provides  a requirement for people to be provisioned a record of the consent transaction.   This addresses multiple privacy principle and privacy legal requirements by providing a framework for operationally addressing multiple Fair Information Practice Principles and likewise ISO 29100 privacy principles.  See Appendix A:
(ref- FIPPs and ISO Principles - "Openness, transparency, notice") and Consent (ISO Principle 1 - "Consent and Choice") are fundamental privacy principles, addressed with this specification.
(editors note:  - how should this be referenced and linked? )

# Status of this document
The v0.8 draft is a  MVCR specification candidate - this draft version is for peer review and not meant for distribution.

## Copyright Notice
Copyright (c) 2016 Kantara and the persons identified as the document authors. All rights reserved.

This document is subject to the [Kantara IPR Policy - Option Patent & Copyright: Reciprocal Royalty Free with Opt-Out to Reasonable and Non-discriminatory (RAND)](https://kantarainitiative.org/confluence/download/attachments/2293776/Kantara%20Initiative%20IPR%20Policies%20_V1.1_.pdf?version=1&modificationDate=1244488630000&api=v2)[HTML version](https://kantarainitiative.org/confluence/pages/viewpage.action?pageId=41025689)

## Table of Contents
1. Objective
2. Scope
2.1 MVCR Modes
3. Notational Conventions For Conformance
4. Terminology
5. MVCR Record Format: Section & Fields
5.1 Header
5.1.1 Example
5.1.2 Guidance
5.2 PI Controller Data
5.2.1 Example
5.2.2 Guidance
5.3 Purpose Specification
5.3.1 Example
5.3.2 Guidance
5.4.	Personally Identifiable Information
guidance
5.5.	Information Sharing
guidance
5.6.	Technical Scope
guidance
6. MVCR Conformance and Compliance
6.1 Example Each mode of conformance and compliance
6.2 Guidance each mode of conformance compliance
7. Appendix A: ISO Terms - mapping and use in the MVCR
8. Appendix B: Scope UMA profile
8. Appendix C: Consent Type -
9. Appendix D: Purpose Categories (or purpose type)

(editors note: added objective and scope to the specification)

## 1.	Objective
This specification identifies the common consent requirements to record a personal information sharing transaction and provide this record as an independent receipt to the individual.

### 2.1 Scope
An MVCR creates a record of a consent to share personal information.

This scope includes how a consent record is provided, how to present the record fields, the timing of the record, the format requirements for  free text fields, linking fields to external information.

The scope of the MVCR covers;
- the provision of the receipt, which includes how a consent record is provided, how to present the record fields, the format for the data fields type of data and order of fields.
- Referencing via link authoritative policy, regulation and consent notice requirements
- documenting the purpose of data sharing categories of purpose for which information is shared,
- documenting the categories of PI
- documenting the technical scopes for the categories  of PI and purpose
- documenting the explicit and non-explicit sharing of personal data


Viable, in this scope, means a record of consent that can be retained and used separately by both issuer (PI Controller) and recipient (PI Subject) as proof of consent.


### 2.2 MVCR Modes

The term 'minimum' in the MVCR refers to the least amount of data required to make an open, compliant, and explicit consent record viable for a number of different contexts, defined by:
* A) the PI Controller, implied and self-asserted
* B) and/or Explicit Consent - defined by explicit reference to authoritative policy i.e. regulation,
* C) and/or Explicit Sharing of PI to specified 3rd Party, ref contract of sharing - defined by scope requirements
* D) and/or defined by technical scope, i.e. attribute level permissions - defined by controller, regulation,  PI Subject, regulation and technical requirement. Type of PI, its purpose, context (Confidentiality, Consent Type, Sensitive Information) and sharing. {PI Category, Purpose Category, Sharing}

The receipt has the Consent Type field in which the scope can be defined as 'Explicit' or a 'Non-Explicit', Consent Type.   Explicit indicates conformance with the MVCR explicit requirements and/or linking to jurisdictional or domain specific notice, and 3rd party sharing consent requirements.
Non-Explicit is non-explicit (for all types of implied consent) and has no compliance claims. Providing flexibility for implementation and adoption without the burden of legal compliance obligations for the implementor. (see conformance table)

(Editors Note: v0.8 has  discussed and is working on consensus for MVCR Lite, which has been the focus of the consent receipt generator (http://api.consentreceipt.org) and the testing for drafting this v0.8.  

In this regard, v0.8 intends to meet the requirement of providing an MVCR lite, but also the structure for the MVCR Lite to be extended. 

The extensions of conformance to explicit consent and for meeting compliance requiremenst are at various levels of spec review and testing by the WG.  As a result v.08 is a Kantara only draft and meant for internal review. (put in URL of kantar demo - here )


### 3 Notational Conventions for Conformance

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC 2119](http://www.rfc-editor.org/info/rfc2119).

 [RFC7159](https://docs.kantarainitiative.org/uma/rec-uma-core.html#RFC7159)

(Editors Note: how do we reference -->  JSON RFC7159 here? JWT - for technically dynamic use of the receipt)


### 4.  Terminology ###
(note: in progress)

Terminology herein leverages where possible,  [ISO/IEC 29100:2011 "Information Technology -- Security techniques -- Privacy Framework"](http://standards.iso.org/ittf/PubliclyAvailableStandards/c045123_ISO_IEC_29100_2011.zip).

(mapping of terms and references in Appendix A)

(editors note: ISO privacy framework should be references, but not used as source of terms as terms should be consent centric not ISO centric)


* **Consent Receipt (CR)**
	A record of a personal information consent transaction.

* **PI Subject **
	See PII Subject in in ISO/IEC 29100:2011, also data subject (EC directive), consenter, PII Subject in NIST 800

* **Explicit Consent**
	 refers to explicit action taken by users which can be explicitly extended to an authoritative reference, scope, and sharing of personal information. Which is required to make a compliance claim.
   * Explicit, for conformance to the MVCR specification, as well as expicit for compliance to legal or authoritative policy, this receit format is used to map the regulation to technical scopes of user owned artefact.  In this regard the specification can extend to maximum explicit and granular requirements for authorisation policy and technical scope.

* ** Non-Explicit Consent **
 (includes self-asserted and externally defined consent type), MVCR Lite Mode demonstrates   receipt  conformance with the MVCR, but is limited to conformance, and makes no compliance claims, but can demonstrate conformance with MVCR using defined consent types.
*

* **Editors Notes on use of explicit in this specification**
* Explicit consent is comprised of the fields that are linked directly to an authoritative reference to ; consent regulation, privacy principles, other consent standards, or industry best practices.  For example: United Kingdom Privacy Laws are used as a conformance example for this specification.
* Explicit is also used to specify the action that a user makes to provide un-ambiguous consent, the action can take the form of an explicit consent action in that a box was ticked, or an 'I agree' button pressed in relation to listed purpose category,
* Explicit is also used in this specification for how purpose is explicitly specified,  each purpose, contains a set of data attributes, with an explicit consent preference, i.e.  a  single purpose with a single check box.
* Explicit sharing this refers to stating that sharing of data for the above purpose categories takes place, the 3rd party it is taking place with, and the link to the contract in which the 3rd party has agreed to abide by this consent.
* Explicit in this specification also refers to technical scopes, in that each scope is separately defined  as to be explicit)

* **Individual**
	see PI Subject in ISO/IEC 29100:2011.

* **Information Sharing**
	A statement or series of statements that set out what information is shared with third parties and for what purpose(s).

* **Minimum Viable Consent Receipt (MVCR)**
	This standard

  **Consent Notice**
 	refers to a notice that is required to inform the consenter what they are consenting too, without it consent is not possible, the quality and usability of the consent notice is what is often used to classify if a consent is legally informed or not, but this varies by jurisdiction context and interpretation.  Consent notices can vary from icons, short notices, direct communication, visceral notice and most often online a policy document like terms of service and privacy policy.

* **Personal Information (PI)**
	See Personally Identifiable Information (PII) in ISO/IEC 29100:2011

* **Personally Identifiable Information**
Personally identifiable information (PII), or Sensitive Personal Information as used in privacy law and information security, is information that can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context. The abbreviation PII is widely accepted in OECD base FIPPs jurisdiction, but the phrase it abbreviates has four common variants based on personal / personally, and identifiable / identifying. Not all are equivalent, and for legal purposes the effective definitions can vary depending on the specific purposes for which the term is being used. (In other countries with privacy protection laws derived from the OECD privacy principles, the term used is more often "personal information", which may be somewhat broader:

* ** PII confidentiality impact levels* 
These refer to low, medium, high confidentiality, or Not Applicable levels, which correspond to NIST controls sp800-122 and can be use for the organisation, the individual and the developer to ascertain on scale the level of risk and security.

* **Purpose Specification**
	A statement or series of statements that set out the purpose(s) for which PII has been collected.
  In the MVCR the purpose is intended to specify the context of use.  

* **Context of Use**
  Organizations should evaluate the context of use to provide the purpose for which the PII is collected, stored, used, processed, disclosed, or disseminated.  The context of use may cause the same PII data elements to be assigned different PII confidentiality impact levels based on their use.  For example, suppose that an organization has two lists that contain the same PII data fields (e.g., name, address, phone number).  The first list is people who subscribe to a general-interest newsletter produced by the organization, and the second list is people who work undercover in law enforcement.  If the confidentiality of the lists is breached, the potential impacts to the affected individuals and to the organization are significantly different for each list.

* **Sensitive Personal Information Categories**
	All sensitive information categories require explicit consent and is subject to legislation and often industry specific regulation and best practice.  Some jurisdictions call out categories of PII specifically, that, by virtue of their sensitivity, require higher levels of protection. The particular categories vary by jurisdiction but will typically include health data (or personal health information - PHI), financial data, political affiliations, sexual orientation, family and personal relationships as defined in law.  In this specification, this field is accompanies by an 'other' field for free text and the Data Controller can define or suggest what is sensitive with a non-explicit 'consent type'.  

## 5. MVCR Record Format: Section & Fields

The MVCR is broken down into 5 sections for usability and to aid in understanding the core function. The 5 sections are:

1.	Header
2.	Data Controller, Contact & Policy
3.	Purpose Specification
4.	Personally Identifiable Information
5.	Information Sharing
6.	Technical Scope
(editors note: added section 6 - technical scope and moved the field scope to this section)

Global Guidance
The order is specific and is part of the specification.
Timing of providing a receipt - needs to be provided at the point in time in which the consent is provided.
The ability for the PI Subject to get a copy of the consent receipt is requirement a requirement

### 2.1 Header

The purpose of this section is to set out the meta-data for the consent transaction. This section will contain the following fields:

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Jurisdiction | Country and if state/prov if applicable | jurisdiction | string. | US  | ISO two-letter country code if applicable, otherwise free text  | to facilitate compliance requirements |  Not Linked |
| Consent Time Stamp | military time | iat | number. Integer number of seconds since 1970-01-01 00:00:00 GMT | 1435367226 | Date and time including time zone, or in UTC that consent was granted  for operational use | for logging consent record | Not Linked |
| Consent Type | title of type model | type | ? (string) | field is used for adding non-explicit consent implied or delayed - or explicit | model consent expectations | Link Optional |
| Collection Method | short 2-3 word description | moc | Method of collection | web form | A description of medium in which the consent was collected | compliance, context of consent | Linked to  location/description of consent  |
| Consent ID | # |  jti |  A unique identifier for the consent receipt | C159A448-A69B-44BF-BFCE-6403FB5D06EE |  A globally unique ID (GUID) | for proof of consent authentication | Not Linked |
| PI Subject | email address, picture, device id,  | sub | string | alice@domain.com | Subject provided identifier, email address - or Claim, defined/namespace | required for proof of consent claim | not linked |

#### Header Example

| Field | Contents|
| ------:	| ------	|
| __Jurisdiction:__ | CA |
| __Consent Time Stamp:__ | 2016/02/08 12:20:34 EST |
| _Consent Type:__ | Explicit |
| __Collection Method:__ | web form | [http://www.consentreceipt.org](http://www.consentreceipt.org) |
| __Consent ID:__ | C159A448-A69B-44BF-BFCE-6403FB5D06EE |
| __PI_Subjct :__ | [roadrunner@fictional.url](mailto:roadrunner@fictional.url) |

#### Header Field Guidance -  TBF
*  Jurisdiction -
* Consent Time Stamp
* Consent type guidance: used for explicit and non-explicit, or defined type, this can explicitly referenced  a global profile for the consent the consent --> receipt - the
 (or N/A in the case where collection is a legal requirement) | Required | **Note 1:** If collection is required by law, consent should not be sought except for other purposes, since consent is only meaningful if the PII Subject may say no. **Note 2:** If the PII is sensitive (below) and consent is required for collection, expressed consent will be required in many jurisdictions
* Collection Method
* Consent ID
* PI Subject

### 2.2 PI Controller Data

This section identifies the individual and company that is accountable for data protection and the privacy policy to which the consent is bound.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| PI Controller | Name of formal entity | controller | object | {"on_behalf": true, "contact": "Dave Controller", "company": "Data Controller Inc.", "address": "123 St., Place", "email": "dave@datacontroller.com", "phone": "00-123-341-2351", "other": }  | name of the data controller | used to identify controller  | linked to controller record or domain |
| On Behalf | yes or no | on_behalf | boolean | true | used to identify the delegate of PI Processor entity acting on behalf of stated organization | used to identify processor if different than controller  | linked |
| Contact Name| [First & Last Name] | contact_name | Jon Doe | contact of pi controller who is processing data | to identify name of personal responsible in accordance with requirements |not linked |
| Contact Address | house #, st, place, country, post code | Physical Address | address | "123 St., Place" | physical address of PI controller | to ascertain location and jurisdiction of responsible entity |  Linked to copy/paste address |
| Contact Email | Email Address | email | string. Email address | jon@datacontroller.com | contact email address | contact in context of consent to manage consent preferences | linked to email address |
| Contact Phone | Phone Number | phone | string. Phone number |  00-000-000-0000 | contact phone number |  a contact field  | Linked |
| Contact Other | Free text | contact_other | string | @twitter | a contact field  |  for social media or other communication channel | Linked directly |
| Privacy Policy | Link to policy | privacy_policy |  http://link.com/privacypolicy | is a link to the current privacy policy |  can be capatured and attached to receipt |  Linked |

#### PI Controller Data Example ####

| Field | Contents|
| ------:	| ------	|
| __Data Controller:__ | Acme Corporation, Inc |
| __On Behalf :__ | null |
| __Contact Name:__ | Mel Blanc |
| __Contact Address:__ | 123 Main Street, Somewhere Else |
| __Contact Email:__ | [mel.blanc@fictional.url](mel.blanc@fictional.url) |
| __Contact Phone:__ | +1 555 555-1212 |
| __Contact Other:__ | @twitter |
| __Privacy Policy:__ | [ACME Privacy Policy](https://www.acme.fictional.url/privacy.policy) |

#### Guidance
* PI Controller - that is accountable for compliance over the PII
* On Behalf
	is used to delegate data controller and or data processing, which maps to the UK's as acting on behalf of the data controller, a third party analytics service would be a processor on behalf of the controller.  When the site operator is acting on behalf of the Data Controller
* Contact Name
* Contact Address
* Contact Email
* Contact Phone
* privacy policy link
	The privacy policy link is to the current policy, if there are materials changes to this policy then a new consent is required for sensitive data categories and various trust network requirements. (note: can be used for compliance- privacy policy can be attached to the receipt payload.

### 2.3 Purpose(s)

This section specifies the purpose(s) for which the PI Controller is collecting PI

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the purpose(s) for collection |
| Service | Site, app, or service | Required | Name of the site, the app or the service that will use the PII collected |
| Purpose | Description of purpose | Required | Should be explicit and specific as reasonably necessary to fulfill the Service |
| Purpose Category | short description | purpose_category | string | for marketing | The primary purpose will be necessary, but may not be the only necessary purpose. PII subject should be able to provide consent directives to opt out of purposes not identified as necessary . |
| PI attributes | multiple PI attributes can be added to a purpose category | used to provide technical scope  | not linked |
| Purpose Preference (Y/N) |  preference | preference | yes | used to distinguish as a secondary purpose separate from the main operational purpose | used to provide purpose scale and distinguish between | linked to preference management settings |
| Purpose Duration/Renewal |

#### Purpose Specification Example (TBF)####

| Service | Purpose | Primary | Necessary |
| ------ | ------ | :------: | :------: |
| __Acme Web Site__ | Core Function | True | True |
| __Acme Web Site__ | Contact Requested | False | False |
| __Acme Web Site__ | Personalized Experience | False | False |
| __Telling PII Subject about other services__ | Marketing | False | False |
| __Telling PII Subject about third party services__ | Marketing Third Parties | False | False |

#### Guidance on Purpose(s)

(TBR)
* Each purpose MUST link the service name to at least one explicit and specific purpose.
* Each purpose SHOULD contain an external reference to an on and off preference for this purpose.
* Each purpose MAY contain additional options. Some examples include a trust mark icon or link, a data retention specification, or a link to the purpose description in the policy.

**Note:** A list of commonly used purposes is provided in Appendix B below.
**Note:** Managing consent directives is out of scope of the MVCR.

### 2.4 Personally Identifiable Information

The purpose of this section is to ensure that the PII Subject is made aware of the types of PII that has been collected and may be used or disclosed.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the types of PII |
| PI Categories | Short description of the category |  |  |
| PI Attribute(s) | used to list attributes that are tracked or automated with authorization scope  |  |  used to map technical scopes in section 6 of the specification |
| PI Confidentiality Level | {low, medium, high, N/A } | con_level | string | low | confidentiality risk level | for security considerations based on purpose and attribute exchange | not linked |
| Sensitive Data Y/N | text | sensitive | string | yes | used to indicate if the receipt contains sensitive data or not in the PII Controller's jurisdiction | used in the specification to determine if the receipt has compliance claims |  Whether or not this type of data is _Sensitive PII_ in  | Required |  |
| Sensitive Information Category |

Sensitive Data
  This is a yes/no question:  can be used for MVCR lite conformance  for non-explicit consent only - which mean its not used for compliance, in this context the "other" field is used to specify sensitivity.    

Sensitive Data
  This is a yes/no question:  can be used for MVCR lite conformance  for non-explicit consent only - which mean its not used for compliance, in this context the "other" field is used to specify sensitivity.    

* **Sensitive Data Categories**
  (optional for compliance claims)
 (not usable for MVCR Lite) Sharing sensitive personal information, is actively regulated and requires explicit consent by all OECD FIPPs based regulations, and for trade of information and technology between jurisdictions.  Use of this field is subject to regulatory requirements.  (Notes:  This field provides the normative baseline for binding practice to laws and standards with Open Consent.  This category is specified, but also flexible so that it can expand to authoritative decisions about new categories and the definition of existing category, like the GDPR which requires consent to be both :  “explicit”  and evidenced by “a statement or by a clear affirmative action” ref GDPR - Doc )
 

 (field is optional, unless for compliance then it is required and linked to authoritative notice, references, and scopes) - these are further specified by jurisdictional legislation, terminology.  Even so,  there are common sensitive data categories for personal information which are enforceable, listed here;  The listing of a sensitive data category in this field indicates this receipt claims to be in conformance and compliance  of compliance requirements.     

The receipt can be further utilized by linking the requirements to the receipt in a way that can be proportionally validated to context.  Providing a context mechanism for trust elevation that can be effectively programed by policy. ( editors note) Which is an inherent requirement for IOT i.e. video surveillance and trust.  

Furthermore, the consent receipt can further be extended with a jurisdictional notice and consent field profile that links to compliance requirements. (See Section X-compliance)  (note: can be delegated by the PI Controller or to 3rd party trust frameworks. using the link)

Note: The use of these features make compliance claims when used

Note: Selecting this field, the receipt MUST be selected as explicit consent, as well as determine the functional notice and consent requirements to be compliant.  These can then be used to specify the such the 'other' field MUST NOT be present when the explicit consent type is selected.  Requirements are supplied by jurisdiction and industry and is out-of-scope of this consent receipt specification.

#### PII Example ####

The example below is for an on-line pharmacy that provides a delivery service

| Category | Description | Sensitive | Explanation |
| ------ | ------ | :------: | :------: |
| __Browser Data__ | Information revealed by the browser to the web server | False | IP address is PII but not sensitive |
| __Address__ | Physical address for deliveries | False | |
| __Health__ | Personal Health Information| True | Specified by regulation in many jurisdictions |
| __Financial__ | Credit Card or payment information | True | Specified by regulation in many jurisdictions |

#### Guidance

Sensitive Personal Information - list of sensitive categories - genetic data, biometric data, and data concerning sexual orientation, can also be define by consentor as sensitive, but needs a subsequent explanation of what is sensitive (includes photographs).

### 2.5 Information Sharing

The purpose of this section is to provide the PII Subject with information about how their information is shared with third parties. In the MVCR this is a Y/N (binary on and off) flag, and if On, then the 3rd parties, the specified purpose and at the minimum the data categories shared may be listed here.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary identify third parties |
| Sharing | Category(ies) of data shared | Required |  |
| Third Party | Third party that receives the data | Required | SHOULD be specific, MAY be generic |
| Purpose | Purpose (only from list above) for sharing data | Required | **Note:** PII provided to vendors or suppliers to the PII Controller that are providing data processing services of PII to the PII Controller would not normally be considered disclosure or information sharing |
| Purpose Category |
| PI Category |
| Duration of Sharing|
| contract/policy |

#### Information Sharing Example

The following example is from an online financial institution

| Sharing | Third Party | Purpose | Explanation |
| ------ | ------ | :------: | :------: |
| __Financial__ | Tax Authority  | Required by Law Enforcement or Government | Financial institution required to disclose personal financial information for tax purposes |
| __Contact__ | Advertising Network| Marketing Third Parties | Ad supported web site |

### Scope(s)   (TBF)
| Receipt Field Label |  scope name | PI Category | PI Purpose |  PI attributes |  Data Type | Example  Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Scope| share 3rd party | name | string. space separated string values | policy reference  [function] withdraw | provide the technical authorization for [function] | linked to policy |  PI Category | purpose category | PI attribute |
| Sub Scope | SUB Scope Name |  PI Attribute for sub scope  |  {Permissions} | sub_scope |s|


####  Scope Example

| Scope  | Purpose | Example | Scope Reference (linked) | Purpose Category | PI Category |
| ------ | ------ | :------: | :------: | :------: | :------: |

| __Browser Data__ | Information revealed by the browser to the web server | Read |  IP address is PII but not sensitive |
| __Address__ | Physical address for deliveries | Read | |
| __Health__ | Personal Health Information| Read + encrypted | linked to notice |
| __Financial__ | Credit Card or payment information | Read + encrypted + specified 3rd party |  |


# 3. Conformance Table

This conformance table specifies requirements to fulfill scope as defined.

| Field # | Field Name | MVCR Lite | Explicit Consent | Legal Compliance UK | Scope |
| ------ | ------ | -----| :------: | :------: | :------: |
| 1 | _Jurisdiction_ | MAY | MUST | MUST - Machine Readable | |
| 2 | _Consent Time Stamp_ | MAY |   MUST - Machine Readable| | |
| 3 | _Consent Type_ | MAY | MUST | Authoritative reference | technical scope for this reference | |
| 4 | _Collection Method_ |  | MAY | | |
| 5 | _Consent ID_ | |  | | |
| 6 | _PI Subject_ | |  | | |
| 7 | _PI Controller_ |
| 8 | _On Behalf_ |
| 9 | _Contact Name_ |
| 10 | _Contact Address_ |
| 11 | _Contact Email_ |
| 12 | _Contact Phone_ |
| 13 | _Contact Other_ |
| 14 | _Privacy Policy_ |
| 15 | Service |
| 16 | Purpose |
| 17 | Purpose Category |
| 18 | PI attributes |
| 19 | Purpose Preference (Y/N) |
| 20 | Purpose Duration/Renewal |
| 21 | PI Categories |
| 22 | PI Attribute(s) |
| 23 | PI Confidentiality Level |
| 24 | Sensitive Data Y/N |
| 25 | Sensitive Information Category |
| 26 | Sharing |
| 27 | Third Party |
| 28 | Purpose |
| Purpose Category |
| PI Category |
| Duration |
| contract/policy |
| 29 | Scope |
| | Sub Scope |

## 3.1. Guidance
### 3.1.1 MVCR Lite : Opening consent by:
* The PI Subject obtains a record of the consent at point in time consent is provided so as to be contextually #usable
* The PI Subject and the Data Controller can use the receipt to communicate about the consent and its management
* The consent receipt can be used by the PI Subject and the Data Controller to prove consent post the point in time the consent was provided
 a contact data is required
* Conformance for MVCR requires a minimum of: contact information, proportional linking, and minimum viable purpose specification

## 3.2 Explicit Consent
* All Core Fields are required, some
* All the requirements of the previous + plus additional fields for the receipt to be usable for scale and compliance

## 3.3 Legal compliance UK (example of compliance requirements)
* All previous requirements + explicit references to requirements and its satisfaction (presented as a X (or UK) profile for compliance)
* Note compliant with current legislation (not GDPR)
* Machine readable is a requirement in order to automate the validation of wether or not a receipt is compliant.
* Conformance Guidance for Explicit Consent Compliance:
the CR purpose is to provide a specific set of requirements for explicit consent, which can be mapped to legislation and regulation  to indicate compliance. The legislation notice requirements for auditing the explicit compliance of a consent receipt can be determined by looking at the jurisdiction and header of the receipt, and to use the purpose, data type and sharing to decipher the type of legislation, the  can be added to the A project kit for a method to map compliance to specific legislation.


# 4. Appendices

## 4.1. All Fields

(IN Progress - completed once - fields drafted)

## 4.2. Appendix A: ISO 29100 Terminology

At the outset of the MVCR it was the intention to move, if possible, this specification to ISO, as well, it was recognized that

>> ISO/IEC 29100:2011 ...provides a privacy framework which can be leveraged in reference to:
>>
>> * specifies a common privacy terminology;
>> * defines the actors and their roles in processing personally identifiable information (PII);
>> * describes privacy safeguarding considerations; and
>> * provides references to known privacy principles for information technology.
>>

ISO/IEC 29100:2011 is applicable to natural persons and organizations involved in specifying, procuring, architecting, designing, developing, testing, maintaining, administering, and operating information and communication technology systems or services where privacy controls are required for the processing of PII."

Although, through the spec work it has become apparent that we can borrow from ISO, but that this specification needs to have within it a specific terminology that is independent of other specifications.  Even so, we adopted Personal Information (rather Personal Data) and like decisions to increase interoperability of this work with this framework.  Here in lies the mapping of terminology and components.

(put in table here mapping elements of MVCR Spec to ISO 29100)
(ref- FIPPs and  (ISO Principles - "Openness, transparency, notice") and Consent (ISO Principle 1 - "Consent and Choice") are fundamental privacy principles, addressed with this specification.
(editors note:  - how should this be referenced and linked? )

A: JSON example

A demonstration version of the MVCR can be found on the [Example Consent Receipt Generator (CRG)](https://mvcr.herokuapp.com/) page. The example site also contains [API documentation](https://mvcr.herokuapp.com/doc/). This server contains a consent receipt generation API. The API consists of a single endpoint at [http://www.consentreceipt.org/mvcr/api](http://www.consentreceipt.org/mvcr/api). This endpoint accepts HTTP POST requests with input in the form of JSON (application/json) documents and returns output in the form of a signed JSON Web Token (application/jwt). The example site consists of two pages:

* The Consent Receipt Generator Input Example and Receipt Rendering page at which users can experiment with inputs and see the corresponding output. This may be used to help develop implementations and see how the consent receipt code is working. The code for this page can be found at [https://github.com/bspk/cr_web](https://github.com/bspk/cr_web).

* A page for API Documentation and examples at [http://api.consentreceipt.org/doc/](http://api.consentreceipt.org/doc/)

The API takes in a JSON document describing the consent transaction for which the receipt is to be generated. This object includes artifacts such as the presiding jurisdiction for the consent action, an identifier for the party consenting. The output of the API is a signed JSON Web Token (JWT) whose payload consists of all of the input data as well as several additional fields. The output JWT is signed by the server using the RS256 algorithm defined in JSON Web Signatures. The server's public key is published in JSON Web Key format at: http://www.consentreceipt.org/api


### JSON Properties

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
| end of object fields | | | |
| policy_uri | string HTTP URL | The internet and immediately accessible privacy policy of the service referred to by the receipt | http://www.example.com/privacy |
| Section 3: Purpose Specification| | List Purposes| |
| purpose | array of string's arrays| Explicit, Specific and Legitimate: interpreted here as: 'Naming the Service' and 'Stating the Active Purpose ' see Appendix B for these requirements| [Bob’s store, delivery, ]or [[" CISWG Membership", "Join"]] |
| Section 4: Sensitive Personal Information | | Identify sensitive PII | |
| sensitive | array of strings | In many jurisdictions their are additional notice and administrative requirements for the collection, storage and processing of what are called Sensitive Personal Information Categories. These are Sensitive in the business, legal, and technical sense, but not specifically in the personal context. This list of categories are required in some jurisdiction, but, the actual notice and purpose requirements are out the scope of the MVCR. | ["health"] |
| Section 5: Information Sharing | | Sharing information with 3rd parties, what categories, with whom, and how information is shared | |
| sharing | object | | |
| Section 5 object fields | | | |
| sharing| array of strings| Data categories to share | None |
| party_name | string | 3rd party to share data | 3rd Party name or 3rd Party Category | |
| purpose| string | How information is shared | None |
| Section 6: Optional or In Review | | | |
| notice | string. HTTP URL | Link to the short notice enables usability and layered policy. to provide enhanced transparency about data collection and information sharing practices | [http://example.com/shortnotice](http://example.com/shortnotice) |
| scopes | string. space separated string values | What you’re allowed to do on the service (these can be tied to legal / business / technical layers) | read update |

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
- 12.	Human Resources – (Records held about employees/ members/ studentsP not elsewhere defined. Incl. HR records such as job title, attendance/disciplinary records. Salary - as opposed to income.)
- 13.	Psychological/Attitudinal – (Inc. religious, political beliefs, sexual orientation and gender identity – though not genetic gender which is Biometric. Traits and personality measures or assessments, but not psychological health - which is health data).
- 14.	Membership – (Political, trade union affiliations, any other opt-in organisational/group membership data - third party organisations only. Includes name of employer when not held by employer. Could extend to online platform membership. Some might be more sensitive than others – may want a separate category)
- 15.	Behavioural – (Any data about the behaviour, habits or movements of an individual - electronic or physical. Location, browser/search history, web page usage (analytics), energy usage (smart meters), login history, calendar data, etc.)
- 16.	Profile – (Marketing and social segmentation data. Any categorisation that impacts information presented or decisions made about an individual. This might be observed or derived data (algorithmic) or volunteered by the individual. Profile data is often generated from Behavioural data).


* **Purpose Specification**
	A statement or series of statements that set out the purpose(s) for which PII has been collected.
  In the MVCR the purpose is intended to specify the context of use.  Context of Use.
  Organizations should evaluate the context of use—the purpose for which the PII is collected, stored, used, processed, disclosed, or disseminated.  The context of use may cause the same PII data elements to be assigned different PII confidentiality impact levels based on their use.  For example, suppose that an organization has two lists that contain the same PII data fields (e.g., name, address, phone number).  The first list is people who subscribe to a general
  -interest newsletter produced by the organization, and the second list is people who work undercover in law enforcement.  If the confidentiality of the lists is breached, the potential impacts to the affected individuals and to the organization are significantly different for each list.

* **Sensitive Personal Information Categories**
	All sensitive information categories require explicit consent and is subject to legislation and often industry specific regulation and best practice.  Some jurisdictions call out categories of PII specifically, that, by virtue of their sensitivity, require higher levels of protection. The particular categories vary by jurisdiction but will typically include health data (or personal health information - PHI), financial data, political affiliations, sexual orientation, family and personal relationships as defined in law.  In this specification, this field is accompanies by an 'other' field for free text and the Data Controller can define or suggest what is sensitive enabling competition and diversity which cannot be specified here.

## 5. MVCR Record Format: Section & Fields

The MVCR is broken down into 5 sections for usability and to aid in understanding the core function. The 5 sections are:

1.	Header
2.	Data Controller, Contact & Policy
3.	Purpose Specification
4.	Personally Identifiable Information
5.	Information Sharing
6.	Technical Scope
(editors note: added section 6 - technical scope and moved the field scope to this section)

Global Guidance
The order is specific and is part of the specification.
Timing of providing a receipt - needs to be provided at the point in time in which the consent is provided.
The ability for the PI Subject to get a copy of the consent receipt is requirement a requirement


### 2.1 Header

The purpose of this section is to set out the meta-data for the consent transaction. This section will contain the following fields:

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Jurisdiction | Country and if state/prov if applicable | jurisdiction | string. | US  | ISO two-letter country code if applicable, otherwise free text  | to facilitate compliance requirements |  Not Linked |
| Consent Time Stamp | military time | iat | number. Integer number of seconds since 1970-01-01 00:00:00 GMT | 1435367226 | Date and time including time zone, or in UTC that consent was granted  for operational use | for logging consent record | Not Linked |
| Consent Type | title of type model | type | ? (string) | field is used for adding non-explicit consent implied or delayed - or explicit | model consent expectations | Link Optional |
| Collection Method | short 2-3 word description | moc | Method of collection | web form | A description of medium in which the consent was collected | compliance, context of consent | Linked to  location/description of consent  |
| Consent ID | # |  jti |  A unique identifier for the consent receipt | C159A448-A69B-44BF-BFCE-6403FB5D06EE |  A globally unique ID (GUID) | for proof of consent authentication | Not Linked |
| PI Subject | email address, picture, device id,  | sub | string | alice@domain.com | Subject provided identifier, email address - or Claim, defined/namespace | required for proof of consent claim | not linked |


#### Header Example

| Field | Contents|
| ------:	| ------	|
| __Jurisdiction:__ | CA |
| __Consent Time Stamp:__ | 2016/02/08 12:20:34 EST |
| _Consent Type:__ | Explicit |
| __Collection Method:__ | web form | [http://www.consentreceipt.org](http://www.consentreceipt.org) |
| __Consent ID:__ | C159A448-A69B-44BF-BFCE-6403FB5D06EE |
| __PI_Subjct :__ | [roadrunner@fictional.url](mailto:roadrunner@fictional.url) |

#### Header Field Guidance -  TBF
*  Jurisdiction -
* Consent Time Stamp
* Consent type guidance: used for explicit and non-explicit, or defined type, this can explicitly referenced  a global profile for the consent the consent --> receipt - the
 (or N/A in the case where collection is a legal requirement) | Required | **Note 1:** If collection is required by law, consent should not be sought except for other purposes, since consent is only meaningful if the PII Subject may say no. **Note 2:** If the PII is sensitive (below) and consent is required for collection, expressed consent will be required in many jurisdictions
* Collection Method
* Consent ID
* PI Subject

### 2.2 PI Controller Data

This section identifies the individual and company that is accountable for data protection and the privacy policy to which the consent is bound.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| PI Controller | Name of formal entity | controller | object | {"on_behalf": true, "contact": "Dave Controller", "company": "Data Controller Inc.", "address": "123 St., Place", "email": "dave@datacontroller.com", "phone": "00-123-341-2351", "other": }  | name of the data controller | used to identify controller  | linked to controller record or domain |
| On Behalf | yes or no | on_behalf | boolean | true | used to identify the delegate of PI Processor entity acting on behalf of stated organization | used to identify processor if different than controller  | linked |
| Contact Name| [First & Last Name] | contact_name | Jon Doe | contact of pi controller who is processing data | to identify name of personal responsible in accordance with requirements |not linked |
| Contact Address | house #, st, place, country, post code | Physical Address | address | "123 St., Place" | physical address of PI controller | to ascertain location and jurisdiction of responsible entity |  Linked to copy/paste address |
| Contact Email | Email Address | email | string. Email address | jon@datacontroller.com | contact email address | contact in context of consent to manage consent preferences | linked to email address |
| Contact Phone | Phone Number | phone | string. Phone number |  00-000-000-0000 | contact phone number |  a contact field  | Linked |
| Contact Other | Free text | contact_other | string | @twitter | a contact field  |  for social media or other communication channel | Linked directly |
| Privacy Policy | URL of the privacy policy as at the time of the receipt | Required | Note that this means that the entity needs to retain copies of prior privacy policies | --- | --- | --- |

#### PI Controller Data Example ####

| Field | Contents|
| ------:	| ------	|
| __Data Controller:__ | Acme Corporation, Inc |
| __On Behalf :__ | null |
| __Contact Name:__ | Mel Blanc |
| __Contact Address:__ | 123 Main Street, Somewhere Else |
| __Contact Email:__ | [mel.blanc@fictional.url](mel.blanc@fictional.url) |
| __Contact Phone:__ | +1 555 555-1212 |
| __Contact Other:__ | @twitter |
| __Privacy Policy:__ | [ACME Privacy Policy](https://www.acme.fictional.url/privacy.policy) |

#### Guidance
* PI Controller - that is accountable for compliance over the PII
* On Behalf
	is used to delegate data controller and or data processing, which maps to the UK's as acting on behalf of the data controller, a third party analytics service would be a processor on behalf of the controller.  When the site operator is acting on behalf of the Data Controller
* Contact Name
* Contact Address
* Contact Email
* Contact Phone
* privacy policy link

### 2.3 Purpose(s)

This section specifies the purpose(s) for which the PI Controller is collecting PI

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the purpose(s) for collection |
| Service | Site, app, or service | Required | Name of the site, the app or the service that will use the PII collected |
| Purpose | Description of purpose | Required | Should be explicit and specific as reasonably necessary to fulfill the Service |
| Purpose Category | short description | purpose_category | string | for marketing | The primary purpose will be necessary, but may not be the only necessary purpose. PII subject should be able to provide consent directives to opt out of purposes not identified as necessary . |
| PI attributes | multiple PI attributes can be added to a purpose category | used to provide technical scope  | not linked |
| Purpose Preference (Y/N) |  preference | preference | yes | used to distinguish as a secondary purpose separate from the main operational purpose | used to provide purpose scale and distinguish between | linked to preference management settings |
| Purpose Duration/Renewal |

#### Purpose Specification Example ####

| Service | Purpose | Preference | Purpose |
| ------ | ------ | :------: | :------: |
| __Acme Web Site__ | Core Function | No | True |
| __Acme Web Site__ | Contact Requested | ON | False |
| __Acme Web Site__ | Personalized Experience | ON | False |
| __Acme Web Site__ | __Telling PII Subject about other services__ | ON | Marketing |  |  |
| __Acme Web Site__ | __Telling PII Subject about third party services__ | OFF | Marketing Third Parties  |

#### Guidance on Purpose(s)

(TBR)
* Each purpose MUST link the service name to at least one explicit and specific purpose.
* Each purpose SHOULD contain an external reference to an on and off preference for this purpose.
* Each purpose MAY contain additional options. Some examples include a trust mark icon or link, a data retention specification, or a link to the purpose description in the policy.

**Note:** A list of commonly used purposes is provided in Appendix B below.
**Note:** Managing consent directives is out of scope of the MVCR.

### 2.4 Personally Identifiable Information

The purpose of this section is to ensure that the PII Subject is made aware of the types of PII that has been collected and may be used or disclosed.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary to set out the types of PII |
| PI Categories | Short description of the category |  |  |
| PI Attribute(s) | used to list attributes that are tracked or automated with authorization scope  |  |  used to map technical scopes in section 6 of the specification |
| PI Confidentiality Level | {low, medium, high, N/A } | con_level | string | low | confidentiality risk level | for security considerations based on purpose and attribute exchange | not linked |
| Sensitive Data Y/N | text | sensitive | string | yes | used to indicate if the receipt contains sensitive data or not in the PII Controller's jurisdiction | used in the specification to determine if the receipt has compliance claims |  Whether or not this type of data is _Sensitive PII_ in  | Required |  |
| Sensitive Information Category |

Sensitive Data
  This is a yes/no question:  can be used for MVCR lite conformance  for non-explicit consent only - which mean its not used for compliance, in this context the "other" field is used to specify sensitivity.    

Sensitive Data Category - (not usable for MVCR Lite) Sharing sensitive personal information, is actively regulated and requires explicit consent by all OECD FIPPs based regulations, and for trade of information and technology between jurisdictions.  Use of this field is subject to regulatory requirements.  (Notes:  This field provides the normative baseline for binding practice to laws and standards with Open Consent.  This category is specified, but also flexible so that it can expand to authoritative decisions about new categories and the definition of existing category, like the GDPR which requires consent to be both :  “explicit”  and evidenced by “a statement or by a clear affirmative action” ref GDPR - Doc )

 (field is optional, unless for compliance then it is required and linked to authoritative notice, references, and scopes) - these are further specified by jurisdictional legislation, terminology.  Even so,  there are common sensitive data categories for personal information which are enforceable, listed here;  The listing of a sensitive data category in this field indicates this receipt claims to be in conformance and compliance  of compliance requirements.     

The receipt can be further utilized by linking the requirements to the receipt in a way that can be proportionally validated to context.  Providing a context mechanism for trust elevation that can be effectively programed by policy. ( editors note) Which is an inherent requirement for IOT i.e. video surveillance and trust.  

Furthermore, the consent receipt can further be extended with a jurisdictional notice and consent field profile that links to compliance requirements. (See Section X-compliance)  (note: can be delegated by the PI Controller or to 3rd party trust frameworks. using the link)

Note: Selecting this field, the receipt MUST be selected as explicit consent, as such the 'other' field should not be present as the explicit consent requirements are supplied by jurisdiction and industry and is out-of-scope of this consent receipt specification.

#### PII Example MVCR Lite ####

The example below is for an on-line pharmacy that provides a delivery service

| Category | Description | Sensitive | Explicit | Explanation |
| ------ | ------ | :------: | :------: |
| __Browser Data__ | Information revealed by the browser to the web server | False | IP address is PII but not sensitive |
| __Address__ | Physical address for deliveries | False | |
| __Health__ | Personal Health Information| True | Specified by regulation in many jurisdictions |
| __Financial__ | Credit Card or payment information | True | Specified by regulation in many jurisdictions |

#### Guidance

Sensitive Personal Information - list of sensitive categories - genetic data, biometric data, and data concerning sexual orientation, can also be define by consentor as sensitive, but needs a subsequent explanation of what is sensitive (includes photographs).

### 2.5 Information Sharing

The purpose of this section is to provide the PII Subject with information about how their information is shared with third parties. In the MVCR this is a Y/N (binary on and off) flag, and if On, then the 3rd parties, the specified purpose and at the minimum the data categories shared may be listed here.

| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | Repeat the following set of fields as many times as necessary identify third parties |
| Sharing | Category(ies) of data shared | Required |  |
| Third Party | Third party that receives the data | Required | SHOULD be specific, MAY be generic |
| Purpose | Purpose (only from list above) for sharing data | Required | **Note:** PII provided to vendors or suppliers to the PII Controller that are providing data processing services of PII to the PII Controller would not normally be considered disclosure or information sharing |
| Sharing Policy/Contact |

#### Information Sharing Example

The following example is from an online financial institution

| Sharing | Third Party | Purpose | Explanation |
| ------ | ------ | :------: | :------: |
| __Financial__ | Tax Authority  | Required by Law Enforcement or Government | Financial institution required to disclose personal financial information for tax purposes |
| __Contact__ | Advertising Network| Marketing Third Parties | Ad supported web site |

### 2.6 Functional Scope
| Receipt Field Label | Receipt Field Format | Data Field Name | Data Type | Example Data Input | Receipt Field Description | Purpose of Field  | Linked |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Scope | scope [function] | --- | --- | string. space separated string values | [function] withdraw | provide the technical authorization for [function] | linked to scope definition |

#### Functional Scope Example
| Sharing | Authority | Purpose | Scope Reference (linked) |
| ------ | ------ | :------: | :------: |
| __Scope__ | UMA  | provide technical authorizations for withdraw of consent  | UMA 1.1  |

# 3. Conformance Table

This conformance table specifies requirements to fulfill scope as defined.

| Field Name | MVCR Lite | Explicit Consent | Legal Compliance UK | Scope |
| ------ | ------ | -----| :------: | :------: | :------: |
Header 
| _Jurisdiction_ | MAY | MUST | MUST - Machine Readable | |
| _Consent Time Stamp_ | MAY |   MUST - Machine Readable| | |
| _Consent Type_ | MAY | MUST | Authoritative reference | technical scope for this reference | |
| _Collection Method_ | MAY  | MAY | | |
| _Consent ID_ | MAY |  | | |
|  _PI Subject_ | MUST |  | | |

| Controller |
|  | _PI Controller_ | MUST | | | |
| | Controller | _On Behalf_ | MUST |
| | Controller | _Contact Name_ |
|  | _Contact Address_ |
|  | _Contact Email_ | MUST one of 10 -13 |
|  | _Contact Phone_ | MUST one of 10 -13 |
|  | _Contact Other_ |MUST one of 10 -13 |
|  | _Privacy Policy_ | MUST |

| Purpose |
| | Service |
|  | Purpose | MUST |
| 17 | Purpose Category | MAY |
| 18 | PI attributes | MAY |
| 19 | Purpose Preference (Y/N) | MAY |
| 20 | Purpose Duration/Renewal | MAY |

| Personal Information | 
| 21 | PI Categories | MAY |
| 22 | PI Attribute(s) | MAY |
| 23 | PI Confidentiality Level | MAY |
| 24 | Sensitive Data Y/N | MUST |
| 25 | Sensitive Information Category | MUST NOT |

Sharing
| 26 | Sharing | MAY |
| 27 | Third Party | MAY |
| 28 | Sharing Purpose |
| 29 | Purpose Category | (note: where do attributes fit in? is their PI Categories )
| Sharing Duration |
| Sharing contract/policy |

Technical
|   Scope |
| Sub Scope |


## 3.1. Guidance
### 3.1.1 MVCR Lite : Opening consent by:
* The PI Subject obtains a record of the consent at point in time consent is provided so as to be contextually #usable
* The PI Subject  and the PII Controller can use the receipt to communicate about the consent and its management
* The consent receipt can be used by the PI Subject and the PII Controller to prove consent post the point in time the consent is provided
 a contact data is required

## 3.2 Explicit Consent
* All Core Fields are required, some
* All the requirements of the previous + plus additional fields for the receipt to be usable for scale and compliance

## 3.3 Legal compliance UK (example of compliance requirements)
* All previous requirements + explicit references to requirements and its satisfaction (presented as a X (or UK) profile for compliance)
* Note compliant with current legislation (not GDPR)
* Machine readable is a requirement in order to automate the validation of wether or not a receipt is compliant.
* Conformance Guidance for Explicit Consent Compliance:
the CR purpose is to provide a specific set of requirements for explicit consent, which can be mapped to legislation and regulation  to indicate compliance. The legislation notice requirements for auditing the explicit compliance of a consent receipt can be determined by looking at the jurisdiction and header of the receipt, and to use the purpose, data type and sharing to decipher the type of legislation, the  can be added to the A project kit for a method to map compliance to specific legislation.


# 4. Appendices

## 4.1. All Fields

(IN Progress - completed once - fields drafted)

## 4.2. Appendix A: ISO 29100 Terminology

At the outset of the MVCR it was the intention to move, if possible, this specification to ISO, as well, it was recognized that

>> ISO/IEC 29100:2011 ...provides a privacy framework which can be leveraged in reference to:
>>
>> * specifies a common privacy terminology;
>> * defines the actors and their roles in processing personally identifiable information (PII);
>> * describes privacy safeguarding considerations; and
>> * provides references to known privacy principles for information technology.
>>

ISO/IEC 29100:2011 is applicable to natural persons and organizations involved in specifying, procuring, architecting, designing, developing, testing, maintaining, administering, and operating information and communication technology systems or services where privacy controls are required for the processing of PII."

Although, through the spec work it has become apparent that we can borrow from ISO, but that this specification needs to have within it a specific terminology that is independent of other specifications.  Even so, we adopted Personal Information (rather Personal Data) and like decisions to increase interoperability of this work with this framework.  Here in lies the mapping of terminology and components.

(put in table here mapping elements of MVCR Spec to ISO 29100)
(ref- FIPPs and  (ISO Principles - "Openness, transparency, notice") and Consent (ISO Principle 1 - "Consent and Choice") are fundamental privacy principles, addressed with this specification.
(editors note:  - how should this be referenced and linked? )

A: JSON example

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

## 4.3. Appendix C: Categories of Personal Information (explainers/examples)

- 1.	Biographical – (General information like Name, DOB, Family info (mother’s maiden name), marital status. Historical data like educational achievement, general employment history.)
- 2.	Contact – (Address, Email, Telephone Number, etc.)
- 3.	Biometric – (Photos, fingerprints, DNA. General physical characteristics – height, weight, hair colour. Racial/ethnic origin or identification - whether self-identified or not)
- 4.	Communications/Social – (Email, message and phone records – both content and metadata. Friends and contacts data.)
- 5.	Network/Service – (Login ids, usernames, passwords, server log data, IP addresses, cookie-type identifiers)
- 6.	Health – (Ailments, treatments, family doctor info. X-rays and other medical scan data)
- 7.	Financial – (This includes information such as bank account, credit card data. Income and tax records, financial assets/liabilities, purchase/sale of assets history.)
- 8.	Official/Government Identifiers – (This includes any widely recognized identifiers that link to individual people. Examples include National Insurance, ID card, Social security, passport and driving license numbers, NHS number (UK). Just the numbers rather than data associated with them.)
- 9.	Social Services/Welfare – (Welfare and benefits status and history)
- 10.	Judicial – (Criminal and police records, inc. traffic offenses.)
- 11.	Property/Asset – (Identifiers of property – license plate numbers, MAC addresses for mobiles, other device identifiers. Not financial assets. Could include digital assets like ebook and digital music data)
- 12.	Human Resources – (Records held about employees/ members/ students not elsewhere defined. Incl. HR records such as job title, attendance/disciplinary records. Salary - as opposed to income.)
- 13.	Psychological/Attitudinal – (Inc. religious, political beliefs, sexual orientation and gender identity – though not genetic gender which is Biometric. Traits and personality measures or assessments, but not psychological health - which is health data).
- 14.	Membership – (Political, trade union affiliations, any other opt-in organisational/group membership data - third party organisations only. Includes name of employer when not held by employer. Could extend to online platform membership. Some might be more sensitive than others – may want a separate category)
- 15.	Behavioural – (Any data about the behaviour, habits or movements of an individual - electronic or physical. Location, browser/search history, web page usage (analytics), energy usage (smart meters), login history, calendar data, etc.)
- 16.	Profile – (Marketing and social segmentation data. Any categorisation that impacts information presented or decisions made about an individual. This might be observed or derived data (algorithmic) or volunteered by the individual. Profile data is often generated from Behavioural data).
