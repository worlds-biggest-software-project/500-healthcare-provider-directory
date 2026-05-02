# Healthcare Provider Directory — Feature & Functionality Survey

> Candidate #500 · Researched: 2026-05-02

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Kyruus Health | Enterprise SaaS | Commercial (acquired by RevSpring) | https://www.kyruushealth.com |
| Zocdoc | Commercial SaaS | Commercial (pay-per-new-patient) | https://www.zocdoc.com |
| Ribbon Health (H1) | API-first SaaS | Commercial B2B API | https://www.ribbonhealth.com |
| Medallion | SaaS | Commercial | https://medallion.co |
| CAQH ProView | Non-profit utility | Free for providers; payer fees | https://www.caqh.org/proview |
| NPPES NPI Registry | Open government data | Free / public domain | https://npiregistry.cms.hhs.gov |

## Feature Analysis by Solution

### Kyruus Health

**Core features**
- Enterprise provider data management platform sitting between a health system's EHR and credentialing systems and the patient-facing "Find a Doctor" directory
- AI-assisted natural language search: patients search with phrases like "cardiologist near me taking Blue Cross" and the system resolves to matching providers
- Real-time appointment availability integration: live slot display from Epic, Cerner, and athenahealth scheduling modules
- Credentialing data ingestion: deep EHR and credentialing system integration maintaining provider data accuracy without manual updates
- Network adequacy reporting: analytics showing network coverage gaps by specialty, geography, and plan

**Differentiating features**
- Covers 425,000+ providers across 1,000+ hospitals and 500+ medical groups — the largest enterprise directory installed base
- Provider data quality engine: automated data quality scoring and discrepancy detection across sources
- RESTful API exposing directory search capabilities to patient access apps, call centre tools, and external scheduling portals

**UX patterns**
- Patient-facing "Find a Doctor" web and mobile search with specialty, location, insurance, and availability filters
- Health system admin console: provider record management, data quality dashboard, and directory publishing workflow
- Referral management integration: directory search embedded in clinical workflows for physician-to-physician referral routing

**Integration points**
- Epic, Oracle Health, athenahealth, and Meditech EHR systems for scheduling and clinical data
- Health system credentialing platforms for primary source verification data
- SMART Scheduling Links for standardised slot discovery across EHR systems

**Known gaps**
- Enterprise-only pricing and implementation (six-figure annual contracts, nine-month deployment)
- No consumer marketplace or booking capability for non-health-system use cases
- Acquired by RevSpring in October 2025; product roadmap direction under new ownership is uncertain

**Licence / IP notes**
- Proprietary SaaS. Directory data model and provider matching algorithms are proprietary.

---

### Zocdoc

**Core features**
- Consumer-facing provider search with real-time appointment scheduling across specialties and locations
- EHR integration for live availability display (Epic MyChart, athenahealth, and others) enabling true real-time slot booking
- Pre-visit intake forms: digital insurance card capture, symptom documentation, and consent forms sent to patients before appointment
- HIPAA-compliant telehealth booking and visit completion within the Zocdoc platform
- Insurance verification: pre-booking insurance eligibility check confirming the provider accepts the patient's plan

**Differentiating features**
- Largest consumer patient audience in the US; 10M+ monthly patient searches
- Partnership with Healthgrades (late 2025): Zocdoc now powers scheduling directly from Healthgrades provider profiles, extending reach
- Patient reviews: post-visit review system with verified reviews from confirmed attendees only

**UX patterns**
- Mobile-first patient experience with map-based provider search and one-tap booking
- Provider calendar availability shown in real time with first available slot highlighted
- Post-visit NPS survey and review prompt sent automatically

**Integration points**
- EHR scheduling APIs: Epic SMART Scheduling Links, athenahealth, and Cerner
- Insurance eligibility verification via Availity and similar clearinghouses
- Provider billing systems for co-pay collection at booking

**Known gaps**
- Credential verification is shallow: NPI cross-check only, not primary source verification of medical licence or board certification
- Not suitable for health system internal credentialing or network management use cases
- Pay-per-new-patient pricing ($35–$110 per patient by specialty) can be expensive for high-volume practices

**Licence / IP notes**
- Proprietary SaaS. Consumer brand and patient review database are key proprietary assets.

---

### Ribbon Health (acquired by H1)

**Core features**
- API-first provider data platform normalising data across NPPES, CAQH ProView, payer directories, and clinical quality sources
- Comprehensive provider attributes: specialties, languages, affiliations, accepted insurance, cost data, and quality ratings from CMS
- Clean address and contact data with deduplication and NPI-to-practice-location resolution
- Insurance panel data: which insurance plans each provider accepts, aggregated from payer directory feeds
- Cost and quality data integration: CMS claims-based quality measures and cost efficiency data per provider

**Differentiating features**
- Best-in-class API design: developer-friendly REST API with clean normalised data, used by health plan apps, digital health startups, and benefits platforms
- Acquired by H1 in January 2025; now part of the largest healthcare professional database globally
- Previously acquired BetterDoctor data assets expanding coverage depth

**UX patterns**
- REST API with comprehensive documentation; no end-user UI — purely a data infrastructure product
- Sandbox environment with test providers for developer integration testing

**Integration points**
- REST API for health plan member portals, care navigation apps, and benefits platforms
- Webhook-based update notifications when provider data changes
- Bulk data export for data warehouse ingestion

**Known gaps**
- No scheduling capability; pure provider data without booking integration
- Data accuracy in rural and underserved markets remains imperfect despite normalisation efforts
- Post-H1 acquisition integration is ongoing; API stability during transition requires monitoring

**Licence / IP notes**
- Proprietary B2B data API. No open-source components. Data compiled from public (NPPES, CMS) and licensed sources.

---

### NPPES NPI Registry

**Core features**
- Authoritative registry of all US National Provider Identifiers (7M+ active NPIs)
- Provider data fields: legal name, credential, taxonomy code (specialty), practice address, phone, and NPI type (individual vs. organisation)
- Free public REST API requiring no authentication, with full dataset weekly download available
- Version 2 NPI download format (V1 deprecated March 3, 2026) introduces extended field lengths and improved data structure

**Differentiating features**
- Authoritative and free: the baseline data layer for every US provider directory without licensing cost
- Complete coverage: every licensed US provider with an NPI is included by definition
- CMS-maintained with regulatory backing: the data standard mandated by HIPAA for US healthcare provider identification

**UX patterns**
- Public web search at npiregistry.cms.hhs.gov for individual provider lookup
- REST API for programmatic NPI validation and basic provider data retrieval
- Bulk download via ZIP file for database seeding

**Integration points**
- Used as the base layer by every commercial provider directory platform (Kyruus, Ribbon, Zocdoc)
- Direct API integration available from any HTTP-capable system
- CMS Plan Finder and Medicare provider directories are built on NPI data

**Known gaps**
- Self-reported data frequently stale: address, phone, and specialty data is often years out of date
- No quality, rating, or scheduling data included
- No insurance acceptance data; specialty taxonomy is coarse-grained (293 taxonomy codes vs. hundreds of colloquial specialties)

**Licence / IP notes**
- Public domain US government data. No copyright or licence restrictions. Free to use commercially without attribution requirement.

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Provider search with specialty, location, and insurance acceptance filtering
- NPPES NPI data as the authoritative base layer for provider identity
- Provider profile with credentials, affiliations, languages, and contact data
- Real-time appointment availability display integrated with EHR scheduling
- Insurance plan acceptance data aggregated from payer directories
- HIPAA-compliant data handling for any patient-linked queries

### Differentiating Features
- AI natural language search resolving plain-language queries to matching provider profiles
- Primary source credential verification beyond NPI: medical licence, board certification, and DEA registration validated against authoritative sources
- Ghost network detection: proactively identifying directory listings where providers cannot actually accept bookings
- Continuous automated data verification replacing 90-day manual re-attestation cycles
- CMS-0057-F FHIR Provider Directory API compliance for regulated payers

### Underserved Areas / Opportunities
- AI-native continuous verification platform: cross-validating provider data across NPPES, state licensing boards, CAQH, and payer contracts in real time rather than periodic batch cycles
- Mid-market credentialing + consumer scheduling combination: Kyruus does deep credentialing but is enterprise-only; Zocdoc does consumer booking but has shallow credentials — the gap between them is unoccupied for digital health and medical group buyers
- Ghost network detection service: proactively identifying providers listed but unable to book as a standalone SaaS feature for health plan compliance teams facing $25K/beneficiary CMS fine exposure
- Open-source FHIR-native directory foundation: a permissively licensed FHIR Plan Net conformant directory that payers can adopt at minimal cost to meet the 2027 CMS Plan Finder mandate

### AI-Augmentation Candidates
- Continuous primary source verification: AI continuously cross-validating provider data against NPPES, state licensing boards, DEA registries, OIG exclusions, and SAM.gov without human initiation
- NLP-powered directory correction: parsing unstructured provider data from payer PDFs, provider websites, and clinical notes to improve accuracy (demonstrated at 93%+ precision/recall in published research)
- Ghost network prediction: ML model flagging listings where the combination of stale address, disconnected phone, and scheduling data mismatch indicates a likely ghost entry
- Natural language provider search: patient-facing interface accepting conversational queries ("I need a Spanish-speaking psychiatrist in Brooklyn who takes Medicaid and can see me this week")

## Legal & IP Summary

NPPES NPI data is US government public domain with no licensing restrictions. FHIR Provider Directory standards (US Core, Da Vinci PDex Plan Net, HL7 NDH) are W3C-licensed HL7 standards with royalty-free use for conformant implementations. CMS-0057-F mandates FHIR API compliance for regulated payers from January 2027, creating a regulatory forcing function for the entire industry. CAQH ProView data is not publicly available for third-party products without a CAQH commercial data licence agreement. Credential data from state medical boards is typically public domain per state open-records laws but access requires individual state API integrations or screen-scraping (with associated legal risk). HIPAA applies to any system that queries provider directories using patient identifiers — query logs tied to patients require Business Associate Agreements. Directory accuracy legislation (No Surprises Act) creates legal exposure for health plans whose directories contain inaccurate data — this is liability transferred downstream from the data accuracy of the platform, not a patent issue. No significant patent barriers identified for building a FHIR-native provider directory platform.

## Recommended Feature Scope

**Must-have (MVP)**:
- FHIR R4 Provider Directory API conformant with Da Vinci PDex Plan Net for payer use cases
- Provider search: specialty, location, insurance acceptance, language, and gender filtering
- NPPES NPI data as the base layer with automated weekly refresh
- Insurance panel data aggregated from major payer FHIR Directory APIs (CMS-0057-F compliant sources)
- HIPAA-compliant architecture with audit logging for patient-linked queries
- Provider profile: credentials, affiliations, locations, and contact data with data source attribution

**Should-have (v1.1)**:
- Primary source credential verification: medical licence status from state licensing board APIs, board certification from ABMS, and OIG exclusion status from daily LEIE check
- Real-time appointment availability via SMART Scheduling Links integration with Epic, athenahealth, and Oracle Health
- Data quality scoring per provider record showing which fields are verified versus self-reported
- CAQH ProView integration (under commercial data licence) for attested provider data
- Ghost network detection: ML-flagging listings where scheduling data and contact accuracy suggest the provider cannot actually accept bookings

**Nice-to-have (backlog)**:
- Continuous automated verification running daily cross-checks against all primary sources without manual re-attestation cycles
- AI natural language patient-facing search resolving conversational queries to provider matches
- Network adequacy analytics: specialty and geography coverage gap analysis for health plan network management
- Open-source FHIR Plan Net directory engine for payers needing low-cost CMS-0057-F compliance
- CMS Plan Finder data submission workflow for Medicare Advantage plan directory publication from 2027
