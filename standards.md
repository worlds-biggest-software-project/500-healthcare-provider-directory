# Standards & API Reference

> Project: Healthcare Provider Directory · Generated: 2026-05-07

## Industry Standards & Specifications

### HL7 FHIR Standards

- **HL7 FHIR R4 (v4.0.1)** — The foundational healthcare interoperability standard. All CMS-mandated APIs require FHIR R4, and it defines the core resource types used in provider directories: Practitioner, PractitionerRole, Organization, Location, HealthcareService, Endpoint, InsurancePlan, and Network. https://hl7.org/fhir/R4/

- **Da Vinci PDex Plan Net Implementation Guide (v1.2.0, STU 1)** — The primary HL7 implementation guide for payer provider directories. Defines FHIR profiles for publishing insurance plan networks, participating organizations, and providers via a standardised API. Based on US Core STU 4 profiles (Practitioner, Organization, Location) and R4 profiles (OrganizationAffiliation, PractitionerRole, HealthcareService, Endpoint). Required for CMS-0057-F compliance. https://hl7.org/fhir/us/davinci-pdex-plan-net/STU1.2/

- **National Directory of Healthcare Providers & Services (NDH) Implementation Guide (v1.0.0 / v2.0.0-current)** — Defines a national directory infrastructure providing a single source of truth for provider, organization, and service data. Supports downstream local directories via FHIR APIs, scheduled exchange, subscriptions, and bulk data export. Includes attestation and verification guidance. https://hl7.org/fhir/us/ndh/

- **US Core Implementation Guide (v9.0.0)** — Defines baseline FHIR profiles for US healthcare, including US Core Practitioner, US Core PractitionerRole, US Core Organization, and US Core Location profiles. These are the foundational profiles upon which provider directory profiles are built. https://build.fhir.org/ig/HL7/US-Core/

- **FHIR Bulk Data Access IG (v3.0.0)** — Standardises bulk export of FHIR resources for large-scale data exchange. Enables efficient export of entire provider directories for data warehouse ingestion, analytics, and directory synchronisation. Uses SMART Backend Services for authorization. https://build.fhir.org/ig/HL7/bulk-data/

- **SMART Scheduling Links** — A FHIR-based specification for clinical appointment slot discovery. Publishers expose Schedule, Slot, and Location resources via a Bulk Publication Manifest ($bulk-publish endpoint). Enables patient-facing tools to discover real-time appointment availability across multiple EHRs. https://github.com/smart-on-fhir/smart-scheduling-links

- **Argonaut Scheduling IG (Release 1.0.0)** — Defines FHIR-based workflows for patient and provider appointment scheduling, including slot search, hold, and book operations. Builds on FHIR Schedule, Slot, and Appointment resources. https://fhir.org/guides/argonaut/scheduling/

### Regulatory Standards

- **CMS-0057-F: Interoperability and Prior Authorization Final Rule** — Mandates four FHIR-based APIs for regulated payers by January 1, 2027: Patient Access API, Provider Access API, Payer-to-Payer API, and Prior Authorization API. The Provider Directory API must be a public, no-authentication FHIR endpoint reflecting provider data changes within 30 days. Requires Da Vinci PDex Plan Net conformance. https://www.cms.gov/cms-interoperability-and-prior-authorization-final-rule-cms-0057-f

- **ONC 21st Century Cures Act Information Blocking Rules** — Prohibits practices that restrict access to electronic health information, including provider directory data. Affects how provider data must be shared across systems and with patients. https://www.healthit.gov/topic/information-blocking

- **No Surprises Act — Provider Directory Requirements** — Requires health plans to verify all provider directory data every 90 days, process updates within two business days, and remove unverified providers. Providers must submit directory information when beginning or terminating network agreements and when material changes occur. Creates legal exposure for plans with inaccurate directories. https://www.cms.gov/nosurprises

- **REAL Health Providers Act (H.R. 7148, enacted February 2026)** — Effective plan year 2028, requires Medicare Advantage organizations to comply with more frequent provider data verification, updated timelines for directory changes, annual accuracy analyses, and public accuracy scores. https://questanalytics.com/news/requiring-enhanced-accurate-lists-of-health-providers-act/

- **NCQA Credentialing Accreditation Standards (2025–2026)** — Governs health plan credentialing programs. Requires internal QI processes, credential verification, sanctions monitoring, and directory information accuracy. The 2025–2026 cycle replaces "system controls" with "information integrity," requiring documented tracking of data changes including what changed, who made the change, when, and why. Surveys effective July 1, 2025 through June 30, 2026. https://www.ncqa.org/programs/health-plans/credentialing/

### Data Model & Classification Standards

- **NUCC Healthcare Provider Taxonomy Code Set** — The standard classification system for US healthcare providers. A ten-character alphanumeric code structured in three levels: Provider Grouping (Level 1), Classification (Level 2), and Area of Specialization (Level 3). Self-selected by providers, used in HIPAA transactions and NPI enumeration. Published twice annually (January and July). https://www.nucc.org/index.php/code-sets-mainmenu-41/provider-taxonomy-mainmenu-40

- **National Provider Identifier (NPI) Standard** — HIPAA-mandated unique identifier for US healthcare providers. Type 1 NPIs identify individual providers; Type 2 NPIs identify organizations. Maintained by CMS via the NPPES registry. Over 7 million active NPIs. https://nppes.cms.hhs.gov/

- **CAQH CORE Operating Rules** — Industry-adopted operating rules for eligibility verification and provider data exchange between payers and providers. Standardises data formats and exchange protocols for credentialing workflows. https://www.caqh.org/core/core-operating-rules

- **OpenAPI Specification (v3.1 / v3.2)** — The industry standard for defining REST API contracts. Version 3.1 achieves full JSON Schema compatibility (Draft 2020-12), enabling precise data model definitions for provider directory API endpoints. Recommended for all non-FHIR API surfaces. https://spec.openapis.org/oas/v3.1.0.html

### Security & Authentication Standards

- **SMART on FHIR (App Launch v2.2.0)** — The standard authentication and authorization framework for FHIR-based healthcare APIs. Built on OAuth 2.0 and OpenID Connect. Defines scopes for patient-level, user-level, and system-level access. Requires PKCE (Proof Key for Code Exchange) for all apps. Supports both EHR launch and standalone launch flows. https://build.fhir.org/ig/HL7/smart-app-launch/

- **SMART Backend Services Authorization** — OAuth 2.0 client credentials flow for server-to-server FHIR API access without user interaction. Uses asymmetric key authentication (JWT assertions signed with private keys). Required for Bulk Data Access and system-level provider directory synchronisation. https://build.fhir.org/ig/HL7/smart-app-launch/backend-services.html

- **HIPAA Security Rule** — Requires administrative, physical, and technical safeguards for electronic Protected Health Information (ePHI). Technical safeguards include access control, audit controls, data integrity, authentication, and transmission security. The 2025 proposed rulemaking would make encryption at rest and in transit mandatory and require multi-factor authentication. https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html

- **NIST SP 800-66 Rev. 2 (February 2024)** — NIST's cybersecurity resource guide for implementing the HIPAA Security Rule. Maps HIPAA standards and implementation specifications to NIST Cybersecurity Framework Subcategories and SP 800-53 security controls. Provides practical risk management activities for healthcare systems. https://csrc.nist.gov/pubs/sp/800/66/r2/final

- **OAuth 2.0 (RFC 6749) and OpenID Connect** — The foundational authorization and authentication protocols underlying SMART on FHIR. OAuth 2.0 provides delegated access via access tokens; OpenID Connect adds identity verification. Required for any patient-facing or provider-facing API surfaces. https://oauth.net/2/

### Government Data Sources & Verification Registries

- **NPPES NPI Registry API** — Free, public, no-authentication REST API providing real-time lookup and validation of National Provider Identifiers. Supports NPI, name, taxonomy, address, and state searches. Bulk download available as weekly CSV/ZIP files. Version 2 download format (effective March 3, 2026) introduces extended field lengths. https://npiregistry.cms.hhs.gov/api-page

- **OIG LEIE (List of Excluded Individuals/Entities)** — HHS Office of Inspector General exclusion database. Available via online search and monthly downloadable CSV files. No official public REST API; integration requires periodic file download and local database synchronisation. Critical for credentialing — excluded providers cannot participate in federal healthcare programs. https://oig.hhs.gov/exclusions/exclusions_list.asp

- **DEA Registration Verification** — Drug Enforcement Administration registration database for controlled substance prescribing authority. API access requires formal application and approval from the DEA Diversion Control Division. Third-party verification services provide authorized API-based access for credentialing workflows. https://deadiversion.usdoj.gov/

- **SAM.gov (System for Award Management)** — Federal government procurement and exclusion database. Entity API provides programmatic access to entity registration and exclusion data. Used in credentialing to verify providers are not debarred from federal programs. https://sam.gov/

## Similar Products — Developer Documentation & APIs

### NPPES NPI Registry
- **Description:** CMS-maintained authoritative registry of all US National Provider Identifiers (7M+ active NPIs). The foundational data layer for every US provider directory.
- **API Documentation:** https://npiregistry.cms.hhs.gov/api-page
- **API Reference (v2.1):** https://npiregistry.cms.hhs.gov/demo-api
- **Bulk Data Download:** https://download.cms.gov/nppes/NPI_Files.html
- **Standards:** REST/JSON, no authentication required
- **Authentication:** None (public API)

### Kyruus Health (RevSpring)
- **Description:** Enterprise provider data management and search platform for health systems and payers. Powers "Find a Doctor" directories with AI-assisted natural language search and real-time EHR scheduling integration.
- **API Documentation:** https://kyruushealth.com/solutions/developers-api/
- **Developer Hub (HealthSparq):** https://developers.healthsparq.com/docs
- **FHIR Interoperability Services:** https://kyruushealth.com/solutions/interoperability-services/
- **Standards:** FHIR R4, Da Vinci PDex Plan Net, CARIN Consumer-Directed Payer Data Exchange, REST/JSON
- **Authentication:** OAuth 2.0 (partner credentials required)

### Zocdoc
- **Description:** Consumer-facing provider search with real-time appointment scheduling. Largest consumer patient audience in the US with 10M+ monthly searches. Public API platform launched for EHR and partner integrations.
- **API Documentation:** https://api-docs.zocdoc.com/apis
- **Developer Guides:** https://api-docs.zocdoc.com/guides
- **Provider Endpoints:** https://api-docs.zocdoc.com/apis/providers
- **Integration Portal:** https://www.zocdoc.com/about/integrate/
- **Standards:** REST/JSON, Sandbox and Production environments
- **Authentication:** API key (partner program enrollment required)

### Ribbon Health (H1)
- **Description:** API-first provider data platform normalising data across NPPES, CAQH, payer directories, and clinical quality sources. Covers demographics, insurance panels, cost data, and quality ratings.
- **API Documentation:** https://ribbon.readme.io/
- **Getting Started Guide:** https://ribbon.readme.io/docs/welcome-to-the-ribbon-health-api
- **Python Client Library:** https://github.com/nikothomas/ribbon-health
- **Standards:** REST/JSON, webhook-based update notifications, bulk data export
- **Authentication:** API key

### Medallion
- **Description:** AI operations platform for automated provider credentialing, licensing, and enrollment. API-first architecture for integrating credentialing workflows with internal systems.
- **API Documentation:** https://docs.medallion.co/docs/reading-the-api-reference
- **Getting Started:** https://docs.medallion.co/docs/getting-started-with-your-api
- **API Basics:** https://docs.medallion.co/docs/common-api-concepts
- **Salesforce Integration:** Available via Salesforce AppExchange
- **Standards:** REST/JSON, OpenAPI-documented
- **Authentication:** API key (secret key in request header)

### Verifiable
- **Description:** AI credentialing and provider network monitoring platform with real-time primary source verification. Connects directly to state boards, NPDB, OIG, and DEA via API.
- **API Documentation:** https://docs.discovery.verifiable.com/
- **Provider Endpoints:** https://docs.discovery.verifiable.com/references/api/providers
- **Authentication Guide:** https://docs.discovery.verifiable.com/references/api/authentication
- **Standards:** REST/JSON, OpenAPI 3.0, Salesforce AppExchange integration
- **Authentication:** API key / OAuth 2.0

### NexHealth
- **Description:** Universal healthcare API connecting to 20+ EHR and practice management systems. Provides scheduling, patient engagement, and provider data via a single unified API.
- **API Documentation:** https://docs.nexhealth.com/reference/introduction
- **Scheduling Guide:** https://docs.nexhealth.com/docs/book-an-appointment
- **Provider Endpoints:** https://docs.nexhealth.com/reference/providers-1
- **Postman Collection:** https://www.postman.com/nexhealth/nexhealth-public/documentation/drh6uj1/8-24-nexhealth-synchronizer-api
- **Standards:** REST/JSON, unified API abstraction over multiple EHR systems
- **Authentication:** API key

### CAQH ProView
- **Description:** Industry-wide provider data repository used by 1,000+ health plans for credentialing and enrollment. Provides attested provider data including demographics, education, licensure, and practice information.
- **API Specification (PDF):** https://www.caqh.org/sites/default/files/solutions/proview/proview-directassure-roster-statuscheck-api-specifications.pdf
- **MuleSoft Connector:** https://docs.mulesoft.com/caqh-connector/latest/
- **Standards:** REST API, basic authentication, commercial data licence required
- **Authentication:** Basic Auth (username/password)

### symplr
- **Description:** Enterprise provider data management platform integrating credentialing, directory, and scheduling. FHIR-compliant APIs for provider search and data exchange.
- **API Documentation:** https://apidoc.symplr.com/
- **Developer Portal:** https://dev-provider.symplr.com/
- **Standards:** FHIR R4, REST/JSON
- **Authentication:** OAuth 2.0 (client_id and client_secret in request header)

### Quest Analytics
- **Description:** Provider network management platform for directory accuracy and network adequacy. Used by CMS and state regulators for compliance assessment. Provides accuracy gap analysis and ML-powered data validation.
- **Platform:** https://questanalytics.com/how-we-help/qes/
- **Accuracy API:** Programmatic retrieval of provider data with error identification and change tracking
- **Accuracy Solutions:** https://questanalytics.com/how-we-help/qes/accuracy/
- **Standards:** REST API, proprietary data model
- **Authentication:** Enterprise credentials (contact sales)

## Notes

- **FHIR R4 is the regulatory baseline.** All CMS-mandated provider directory APIs require FHIR R4 (v4.0.1). FHIR R5 and the forthcoming R6 are not yet required by regulation, though the NDH IG v2.0.0 is tracking toward R5 alignment.

- **No official OIG LEIE REST API exists.** Provider exclusion checking requires downloading monthly CSV files and building a local synchronisation process. This is a significant integration gap that an AI-native platform could address with automated daily reconciliation.

- **DEA verification is access-restricted.** Unlike the NPPES NPI registry (public, no auth), DEA registration lookup requires formal application and approval. Most credentialing platforms use authorised third-party verification services rather than direct DEA API access.

- **State medical board APIs are fragmented.** Each US state maintains its own licensing board with varying levels of API availability. Some states offer public lookup APIs; others require screen-scraping or manual verification. This fragmentation is one of the most significant technical challenges for automated credentialing and represents a strong opportunity for AI-native automation.

- **The January 2027 CMS-0057-F deadline is the primary market forcing function.** Regulated payers (Medicare Advantage, Medicaid managed care, ACA marketplace plans) must publish FHIR-compliant provider directories by this date, creating immediate demand for standards-conformant directory platforms.

- **The REAL Health Providers Act (2026) introduces public accuracy scores.** Starting in plan year 2028, Medicare Advantage directory accuracy will be publicly reported, raising the stakes for directory data quality and creating a new competitive dimension for provider directory platforms.
