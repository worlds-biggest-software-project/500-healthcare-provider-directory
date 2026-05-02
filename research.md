# Healthcare Provider Directory

> Candidate #500 · Researched: 2026-05-02

## Existing Products and Software Packages

### 1. Zocdoc
**Type:** Commercial SaaS · **Credentialing depth:** Low (NPI-based)

Consumer-facing provider search with real-time appointment scheduling. Integrates with EHR systems for live availability. In late 2025, Zocdoc partnered with Healthgrades to power booking directly from Healthgrades search results.

- **Strengths:** Massive consumer reach, EHR integration, real-time slot availability, pre-visit intake forms, HIPAA-compliant telehealth.
- **Weaknesses:** Credential verification is shallow (NPI cross-check only, not primary source); not suitable for health system internal directories.
- **Pricing:** Pay-per-new-patient only ($35–$110 depending on specialty and region).

### 2. Healthgrades
**Type:** Commercial SaaS · **Credentialing depth:** Low (NPI + claims)

Profiles for essentially every NPI-registered provider in the US, enriched with 10M+ patient ratings and CMS-derived hospital quality ratings. Scheduling now powered by Zocdoc (late 2025 partnership).

- **Strengths:** Broadest US provider coverage, outcome-based quality ratings, strong consumer brand.
- **Weaknesses:** Data quality depends on whether providers claim/update profiles; credential depth limited.
- **Pricing:** Free basic listings; paid profile enhancement and advertising for providers.

### 3. Kyruus Health
**Type:** Commercial SaaS (enterprise) · **Credentialing depth:** High (EHR + credentialing systems)

The leading enterprise provider data management platform. Sits between a health system's EHR/credentialing systems and its patient-facing "Find a Doctor" directory. Covers 425,000+ providers across 1,000+ hospitals and 500+ medical groups. Acquired by RevSpring (Frazier Healthcare) in October 2025.

- **Strengths:** Deep EHR integration, real-time availability scheduling, AI-assisted natural language search, strong market share with large IDNs.
- **Weaknesses:** Enterprise-only pricing, high implementation complexity, not suited for smaller practices, no consumer marketplace.
- **Pricing:** Custom enterprise contracts; six-figure annual deals; projected $150M+ ARR in 2025.

### 4. Ribbon Health (acquired by H1, January 2025)
**Type:** Commercial SaaS / API-first · **Credentialing depth:** Medium–High

API-first provider data platform used by health plans, digital health startups, and benefits platforms. Normalises data across NPI, CAQH, payer directories, and clinical quality sources. Previously acquired BetterDoctor data assets. Acquired by H1 for undisclosed sum; had raised ~$55M (a16z, General Catalyst, YC).

- **Strengths:** Best-in-class API design for developers, clean normalised data, includes cost and quality data, insurance acceptance data.
- **Weaknesses:** No scheduling capability; data accuracy still imperfect in rural markets; purely B2B infrastructure.
- **Pricing:** B2B API licensing by query volume; not public.

### 5. BetterDoctor (now part of Quest Analytics)
**Type:** Commercial data platform · **Credentialing depth:** High (attested)

Pivoted from consumer physician search to B2B provider data attestation. 700,000+ providers have directly attested their information through the platform, feeding health plan CMS compliance workflows.

- **Strengths:** Large attested provider dataset, purpose-built for CMS 90-day accuracy compliance (Medicare Advantage).
- **Weaknesses:** No longer a consumer product; narrower focus than Ribbon Health.
- **Pricing:** Enterprise licensing through Quest Analytics; not public.

### 6. Solv Health
**Type:** Commercial SaaS · **Credentialing depth:** Low

Mobile-first platform for urgent care and same-day appointment search and scheduling. AI-powered queue blending for walk-ins and booked patients. Full EHR integration achievable in ~6 weeks.

- **Strengths:** Purpose-built for urgent/same-day workflows, 30% booking conversion improvement claimed, strong consumer app.
- **Weaknesses:** Narrow focus (urgent/primary only); no credential verification layer; not suited to specialist scheduling.
- **Pricing:** Per-location pricing (not per-user); annual/quarterly/monthly terms; custom proposals.

### 7. Doximity
**Type:** Commercial SaaS / professional network · **Credentialing depth:** Very high

Professional network for US clinicians with >85% of US physicians verified as members. Uses credential documents, licenses, DEA numbers, and institutional email (average 3-day verification turnaround). Expanding into AI tools (DoxGPT, PeerCheck) with 100+ health systems on enterprise access in 2026.

- **Strengths:** Highest-quality physician verification in the market, massive network effect, consumer-searchable public directory.
- **Weaknesses:** Not a scheduling platform; primarily physician-facing rather than patient-facing booking.
- **Pricing:** Free for clinicians; revenue from pharma/health system enterprise contracts.

### 8. CAQH ProView
**Type:** Non-profit industry utility · **Credentialing depth:** Very high

The de facto national credentialing data repository where 2.5 million healthcare providers fill out credentials once and share with 1,000+ health plans. Providers re-attest every 120 days. Not an API product for developers; not consumer-facing.

- **Pricing:** Free for providers; health plans pay participation fees (not public).

### 9. NPPES / NPI Registry (CMS)
**Type:** Free open government data and API

Authoritative registry of all US National Provider Identifiers (NPIs). 7M+ active NPIs with name, taxonomy, address, and contact data. Public REST API with no authentication required.

- **Strengths:** Authoritative, free, covers every licensed US provider, base layer for virtually every other platform.
- **Weaknesses:** Self-reported and often stale; no quality/rating data; no scheduling; address accuracy is notoriously poor.
- **Pricing:** Completely free, public domain.

### 10. Availity
**Type:** Commercial SaaS (healthcare network) · **Credentialing depth:** High (payer-facing)

The largest US healthcare intelligence network — 3 million credentialed providers, 13 billion transactions/year, 170 million covered lives. Provider Lifecycle Solution manages payer-side onboarding, credentialing intake, and data management. One case study: 95% automation of provider registrations, approval time reduced from months to weeks.

- **Weaknesses:** Payer-facing, not patient-facing; no scheduling; not API-first.
- **Pricing:** Free basic portal; enterprise contracts for lifecycle solutions.

### 11. Medallion
**Type:** Commercial SaaS · **Credentialing depth:** High

AI-powered provider credentialing infrastructure covering ~1 million providers (~10% of US). Raised $43M Series B in August 2025 (Acrew Capital, Sequoia, GV); total funding $130M. Positioning as the "national credentialing clearinghouse."

### 12. Certify (CertifyOS)
**Type:** Commercial SaaS · **Credentialing depth:** High

Provider data management platform focused on digital health and tech-enabled care companies. Raised $40M Series B (Transformation Capital, General Catalyst) in June 2025; total funding $69M. Tripled YoY growth.

---

## Relevant Industry Standards or Protocols

### FHIR Provider Directory Standards (HL7)

**HL7 FHIR US Core — Practitioner and PractitionerRole Profiles (STU 8.0.0)**
Mandatory conformance floor for all ONC-certified health IT systems. Defines baseline data elements for representing practitioners, their roles, specialties, locations, and endpoints. All other directory IGs extend these profiles.
URL: https://build.fhir.org/ig/HL7/US-Core/

**HL7 Da Vinci PDex Plan Net (STU 1.2.0)**
Primary US payer-focused FHIR Implementation Guide. Defines how health insurers publish their provider networks via FHIR APIs. Key resources: `Organization`, `Practitioner`, `PractitionerRole`, `Location`, `HealthcareService`, `InsurancePlan`, `Network`. Mandated by CMS-0057-F for regulated payers.
URL: https://build.fhir.org/ig/HL7/davinci-pdex-plan-net/

**HL7 National Directory of Healthcare Providers & Services (NDH) (STU 1.0.0)**
US-specific evolution of VHDir, envisioning a single national source of truth for all providers and organisations with downstream FHIR API consumption. The target architecture for a national-scale directory.
URL: http://hl7.org/fhir/us/ndh/

**HL7 Validated Healthcare Directory (VHDir)**
International FHIR IG underpinning Plan Net and NDH. Introduces the `VerificationResult` resource for tracking primary source verification outcomes per data element — directly maps to NCQA credentialing workflows.
URL: http://hl7.org/fhir/uv/vhdir/

### CMS Regulatory Requirements

**CMS Interoperability and Prior Authorization Final Rule (CMS-0057-F)** (January 2024)
Requires Medicare Advantage, Medicaid, CHIP, and ACA Marketplace plans to publish a publicly accessible, no-auth FHIR Provider Directory API implementing Da Vinci PDex Plan Net. Data must be updated within 30 days of changes. Full compliance deadline: January 1, 2027. Penalties: $25,000 to several million dollars for non-compliance. Active enforcement began October 2025.
URL: https://www.cms.gov/priorities/burden-reduction/overview/interoperability/policies-regulations/cms-interoperability-prior-authorization-final-rule-cms-0057-f

**No Surprises Act — Provider Directory Accuracy Requirements**
Mandates 90-day verification cycles for all directory entries, updates within 2 business days of provider changes, and a minimum 85% accuracy rate for MA and ACA Marketplace plans. From plan year 2027, MA organisations must submit directory data to CMS for publication on Medicare Plan Finder. Penalties up to $10,000 per violation for incorrect network status.

### Provider Identifiers and Credentialing Infrastructure

**NPPES NPI Registry (CMS)**
Authoritative registry of all US National Provider Identifiers. Public REST API, no authentication. Note: Version 1 of monthly/weekly download files deprecated March 3, 2026; Version 2 introduces extended field lengths.
URL: https://npiregistry.cms.hhs.gov/api-page

**CAQH ProView / Primary Source Verification (PSV)**
De facto national credentialing platform; 2.5 million providers, accepted by 1,000+ health plans. PSV validates credentials against licensing boards, medical schools, and government registries. Integrates with CAQH Provider Data Management platform.

**CAQH VeriFide and SanctionsTrack**
Automated primary source verification (VeriFide) and ongoing sanctions monitoring against OIG LEIE and SAM.gov (SanctionsTrack).

**CAQH CORE Operating Rules**
Interoperability operating rules for healthcare transactions. Relevant when directory systems also handle eligibility verification.

### Credentialing Accreditation Standards

**NCQA Credentialing Standards** (major 2025 update, effective July 1, 2025)
Industry gold standard for credentialing accreditation and certification. 2025 changes: shortened PSV timeframes (120 days accreditation / 90 days certification); mandatory continuous monitoring software running daily checks against OIG LEIE, SAM.gov, and state medical boards; voluntary collection of provider demographic data (race, language, ethnicity).
URL: https://www.ncqa.org/programs/health-plans/credentialing/

### Information Blocking and Certification

**21st Century Cures Act / ONC Certification** (Final Rule May 2020)
Certified health IT must implement FHIR R4-based APIs. Information blocking prohibitions prevent unreasonable restriction of access to electronic health information, including provider directory data.

### Health Information Exchange

**DirectTrust**
Non-profit governing push-based health information exchange (Direct Messaging). Maintains a directory of validated provider endpoint addresses; relevant for provider-to-provider communication endpoints in a directory.
URL: https://directtrust.org/standards

**Carequality (The Sequoia Project)**
Technology-agnostic nationwide interoperability framework. Maintains a participant directory listing every HIE, healthcare provider, and network actor — a registry of exchange endpoints required to route data across Epic, CommonWell, Surescripts networks.
URL: https://carequality.org/

### Scheduling Integration Standards

**SMART Scheduling Links (HL7 IG)**
Lightweight FHIR IG for structured slot discovery and deep-link-based booking across multiple EHRs and booking portals. Actively used by Zocdoc and Optum as of 2025. 2025 enhancements added `PractitionerRole` as a linkable resource for Schedules and Slots.
URL: https://github.com/HL7/smart-scheduling-links

**Argonaut Scheduling IG**
Vendor-agnostic FHIR RESTful API specification for patient and practitioner appointment booking using `Schedule`, `Slot`, and `Appointment` FHIR resources.
URL: https://fhir.org/guides/argonaut/scheduling/

**IHE FHIR Scheduling Profile (ITI.Scheduling)**
IHE governance overlay on top of Argonaut for cross-enterprise scheduling.
URL: https://profiles.ihe.net/ITI/Scheduling/

### Privacy and Compliance

**HIPAA Privacy Rule**
Provider directory data (name, NPI, specialty, contact) is generally not PHI. However, query logs tied to patient identifiers could constitute PHI. Business Associate Agreements required when vendor processing could be linked to patient records. De-identification (Safe Harbor or Expert Determination) required if patient utilisation data informs directory accuracy.

---

## Available Research Materials

**Busch, S. H., & Kyanko, K. A. (2020).** Incorrect Provider Directories Associated With Out-Of-Network Mental Health Care And Outpatient Surprise Bills. *Health Affairs*, 39(6), 975–983. DOI: 10.1377/hlthaff.2019.01501 · *Peer-reviewed.*
National survey finding 53% of patients using mental health directories encountered inaccuracies; those who did were 4× more likely to receive surprise out-of-network bills.

**Sacarny, A., Daw, J. R., & Morden, N. E. (2023).** Consistency of Physician Data Across Health Insurer Directories. *JAMA*, 329(11), 940–942. PMC: PMC10015301 · *Peer-reviewed.*
Cross-insurer comparison of 40%+ of US physicians across UnitedHealth, Elevance, Cigna, Aetna, and Humana; only 19.4% had consistent address and specialty data across all five directories.

**Haeder, S. F., & Zhu, J. M. (2024).** Inaccuracies in provider directories persist for long periods of time. *Health Affairs Scholar*, 2(6), qxae079. DOI: 10.1093/haschl/qxae079 · *Peer-reviewed.*
Two-stage secret shopper study of Pennsylvania ACA Marketplace plans; 40.3% of inaccurate listings persisted for 540+ days despite No Surprises Act 90-day update requirements.

**Burman, A., & Haeder, S. F. (2022).** Potemkin Protections: Assessing Provider Directory Accuracy and Timely Access for Four Specialties in California. *Journal of Health Politics, Policy and Law*, 47(3), 319–349. DOI: 10.1215/03616878-9626866 · *Peer-reviewed.*
Analysis of California DMHC survey data; consumers could schedule urgent care with only 28–54% of directory-listed providers.

**Burman, A., Haeder, S. F., & Xu, W. Y. (2023).** Provider directory inaccuracy and timely access for mental health care. *American Journal of Managed Care*, 29(2), 96–102. PubMed: PMID 36811984 · *Peer-reviewed.*
California statewide analysis of 1.1 million mental health directory observations; high rates of inaccuracy and access barriers documented.

**Butala, N. M., Jiwani, K., & Bucholz, E. M. (2024).** Characterizing physician directory data quality: variation by specialty, state, and insurer. *BMC Health Services Research*, 24, 808. DOI: 10.1186/s12913-024-11269-5 · *Peer-reviewed.*
Examined consistency of address, phone, and specialty data across five national insurer directories; found widespread variation by specialty and geography.

**Mowery, D. L., South, B. R., Christensen, L., Leng, J., & Samore, M. H. (2019).** Facilitating accurate health provider directories using natural language processing. *BMC Medical Informatics and Decision Making*, 19, 60. DOI: 10.1186/s12911-019-0788-x · *Peer-reviewed.*
NLP pipeline applied to Connecticut state and federal records to identify and correct provider directory entries; precision 0.93, recall 0.95, recovering 6,849 of 7,177 records.

**Knight, D. R. T., et al. (2023).** Artificial intelligence for patient scheduling in the real-world health care setting: A metanarrative review. *Health Policy and Technology*, 12(4), 100824. DOI: 10.1016/j.hlpt.2023.100824 · *Peer-reviewed.*
Mayo Clinic and Duke metanarrative review synthesising evidence on AI/ML scheduling tools across appointment management, no-show prediction, and resource optimisation.

**U.S. Senate Committee on Finance, Majority Staff (2023).** Barriers to Mental Health Care: Improving Provider Directory Accuracy to Reduce the Prevalence of Ghost Networks. U.S. Senate. URL: finance.senate.gov · *Government report (not peer-reviewed).*
Secret shopper study of 12 Medicare Advantage plans across 6 states; only 18% of contacted directory listings resulted in a bookable appointment.

**U.S. Government Accountability Office (2015).** Medicare Advantage: Actions Needed to Enhance CMS Oversight of Provider Network Adequacy. GAO-15-710. Washington, DC: GAO. URL: gao.gov/products/gao-15-710 · *Government report (not peer-reviewed).*
Foundational oversight report finding CMS lacked adequate tools to verify MA network adequacy; recommendations only partially implemented as of subsequent reviews.

---

## Market Research

### Market Size

**Provider Network Management (closest TAM proxy):**
- Market Research Future: $2.61B (2024) → $5.43B (2035), ~7% CAGR
- Zion Market Research: $5.09B (2024) → $20.64B (2034), ~15% CAGR

*Note: Wide range reflects definitional inconsistency across analysts — some include contract management and network adequacy analytics alongside directory functions. The ~7% CAGR estimate is the more conservative and credible midpoint.*

**Provider Credentialing Software:**
- Grand View Research: $808M globally (2023) → $1.42B (2030), 8.3% CAGR
- U.S. market specifically: $267.7M (2024), ~7% CAGR through 2033

**Healthcare Scheduling Software:**
- Grand View Research: $318M (2023), 13.3% CAGR
- U.S. staffing + scheduling segment: $1.85B (2024) → $5.68B (2034), ~12% CAGR

Scheduling is growing faster than credentialing, driven by patient-facing digital access demands and post-COVID consumerisation of healthcare.

### Provider Universe

- 1,082,187 actively licensed physicians in the US (FSMB Census, 2024)
- 385,000+ licensed nurse practitioners (BLS/AANP, 2024; projected +35% by 2034)
- 17M+ total healthcare workers (HRSA, 2023)

### Payer Universe

- ~1,100 health insurance companies operate in the US (NAIC, 2024)
- Concentration is extreme: the top 5 carriers (UnitedHealth, Kaiser, Elevance, Centene, HCSC/BCBS) control roughly half of covered lives
- ~800+ Medicare Advantage plan names across ~400 organisations (CMS)
- Real enterprise SaaS buyer count: ~20–30 national/regional payers represent the majority of procurement budget; hundreds of health systems

### Pricing Signals

All enterprise pricing is negotiated and not publicly disclosed. Available proxies:
- Per-provider/month (credentialing platforms): estimated $150–$400
- Enterprise annual contracts (large health systems / payers): estimated $250K–$2M+
- Kyruus Health implied blended rate: ~$25/provider/month (extrapolated from $150M+ ARR and 500K+ providers — treat as rough approximation only)

### Key Buyer Personas

| Buyer | Primary Pain Points |
|---|---|
| Health Plans / Payers (VP Network Management, CMO) | CMS fines up to $25K/beneficiary, ghost networks, 85% accuracy threshold, No Surprises Act liability |
| Health Systems / Hospitals (CIO, VP Patient Access) | Patient leakage, scheduling friction, provider data silos across EHR/credentialing/scheduling systems |
| Medical Groups / MSOs (COO, credentialing staff) | Manual credentialing workflows, payer enrollment delays, time-to-bill gaps |
| Patients / Consumers | Inaccurate directories leading to surprise bills or inability to book; 4× higher surprise-bill risk |

Enterprise sales cycles of 9–18 months; 6–10 stakeholder buying groups with CIO/CFO as final approvers.

### Directory Accuracy — The Core Problem

| Source | Finding |
|---|---|
| CMS national audit (rounds 2 & 3) | 48.7–52.2% of provider locations had at least one inaccuracy |
| JAMA (5 large insurers, 2023) | 81% of directory entries inaccurate; only 19.4% consistently accurate across all five insurers |
| Health Affairs Scholar (2024) | 40% of inaccurate entries persisted 540+ days post-No Surprises Act |
| Senate Finance Committee secret shopper (2023) | Only 18% of listed mental health providers resulted in a bookable appointment |

### Recent Funding and M&A Activity

| Company | Event | Date | Notes |
|---|---|---|---|
| Kyruus Health | Acquired by RevSpring (Frazier Healthcare) | October 2025 | Had raised $196M total; projected $150M+ ARR; profitable since 2023 |
| Ribbon Health | Acquired by H1 | January 2025 | Had raised ~$55M (a16z, General Catalyst, YC) |
| Medallion | $43M Series B (Acrew Capital, Sequoia, GV) | August 2025 | Total funding $130M; covers ~1M providers |
| Certify (CertifyOS) | $40M Series B (Transformation Capital, GC) | June 2025 | Total funding $69M; tripled YoY growth |

**Signal:** Both dominant pure-play directory companies (Kyruus, Ribbon) were acquired within months of each other, consolidating into larger patient engagement (RevSpring) and healthcare analytics (H1) platforms. Infrastructure-layer players (Medallion, Certify) remain independent and well-funded, betting on being the data backbone regardless of who acquires the application layer.

### Regulatory Enforcement Timeline

- October 2025: CMS active enforcement of CMS-0057-F begins
- January 1, 2026: MA payers begin reporting prior authorisation metrics; must submit directory data to CMS
- January 1, 2027: Full CMS-0057-F API compliance deadline; MA plans must publish via CMS Plan Finder (removing ability to self-host standalone directories)

---

## AI-Native Opportunity

Based on the above research:

- **Continuous verification, not batch attestation.** Every existing platform relies on periodic re-attestation (90–120 day cycles) or manual curation. An AI-native system could continuously cross-validate provider data across NPPES, state licensing boards, CAQH, DEA registries, and payer contracts in real time — the 40% persistence of inaccuracies for 540+ days is a direct consequence of batch-only workflows.

- **The credentialing + consumer scheduling gap is real and unoccupied.** Kyruus does credentialing-depth data but is enterprise-only with no consumer booking. Zocdoc does consumer booking but has shallow credentials. No open-source or affordable product bridges both layers. An AI-native tool targeting digital health startups, medical groups, and mid-market health plans is an underserved segment.

- **NLP for unstructured provider data normalisation.** Mowery et al. (2019) demonstrated 93%+ precision/recall for NLP-driven directory correction. Modern LLMs could extend this to freeform provider bios, multilingual data, and cross-format normalisation — reducing the expensive human review that makes credentialing slow.

- **Ghost network detection as a core feature.** The 80%+ "ghost" rate in Medicare Advantage directories is documented, politically salient (Senate Finance Committee investigations), and now carries $25K/beneficiary CMS fine exposure. An AI-native tool that proactively flags likely ghost entries — based on call patterns, scheduling data, and cross-source inconsistency — addresses the highest-stakes buyer pain point.

- **Open-source FHIR-native foundation lowers cold-start barrier.** NPPES NPI is free, FHIR Plan Net and NDH are open standards, and the CMS Plan Finder mandate (2027) requires payers to expose FHIR APIs. An open-source tool built on these foundations can achieve 80%+ data coverage from day one without licensing incumbent data providers.
