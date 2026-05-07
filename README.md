# Healthcare Provider Directory

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> A credentialing-verified provider search and scheduling platform that replaces fragmented, error-prone healthcare directories with a FHIR-native, continuously verified data layer.

Healthcare Provider Directory is an open-source platform for health systems, payers, and medical groups that need accurate, standards-compliant provider data integrated with real-time scheduling. It addresses the persistent problem of directory inaccuracy -- studies show 30-50% of provider directory entries contain errors -- by combining authoritative public data sources with AI-driven continuous verification.

---

## Why Healthcare Provider Directory?

- **Directory accuracy is broken.** Incumbent directories rely on 90-day manual re-attestation cycles, leaving 30-50% of entries with stale addresses, phone numbers, or insurance acceptance data. Ghost networks -- providers listed but unable to accept bookings -- expose payers to CMS fines of up to $25K per affected beneficiary.

- **Enterprise incumbents are inaccessible to mid-market buyers.** Platforms like Kyruus and symplr command six-figure annual contracts with nine-month deployment timelines, pricing out digital health companies, medical groups, and smaller health plans.

- **Consumer and credentialing are artificially separated.** Zocdoc handles patient-facing search and booking but performs only shallow NPI-based credential checks. Credentialing platforms like HealthStream and Medallion verify credentials deeply but offer no patient scheduling. The gap between these two worlds is unoccupied.

- **Regulatory mandates are creating urgency.** CMS-0057-F requires regulated payers to publish FHIR-accessible provider directories by January 2027. Many payers lack the technology to comply without expensive vendor engagements.

- **No open-source FHIR-native directory exists.** Every current provider directory platform is proprietary. A permissively licensed FHIR Plan Net conformant directory would let payers meet the CMS mandate at minimal cost.

---

## Key Features

### Provider Search and Discovery

- Specialty, location, insurance acceptance, language, and gender filtering
- AI natural language search resolving conversational queries (e.g. "Spanish-speaking psychiatrist in Brooklyn who takes Medicaid")
- Provider profiles with credentials, affiliations, locations, and contact data with data source attribution
- Map-based search with first-available appointment highlighting

### Credential Verification

- Primary source verification against state licensing boards, ABMS board certification, DEA registration, and OIG exclusion lists
- Continuous automated cross-validation replacing manual 90-day re-attestation cycles
- Data quality scoring per provider record showing verified versus self-reported fields
- CAQH ProView integration for attested provider data

### Scheduling Integration

- Real-time appointment availability via SMART Scheduling Links integration with Epic, athenahealth, and Oracle Health
- Live slot display from major EHR scheduling modules
- Patient self-booking with pre-visit insurance eligibility verification

### Directory Integrity

- Ghost network detection: ML-based flagging of listings where scheduling data, contact accuracy, and address validity suggest the provider cannot accept bookings
- Automated NPPES NPI data refresh on weekly cadence
- Insurance panel data aggregated from major payer FHIR Directory APIs
- Webhook-based update notifications when provider data changes

### Compliance and Standards

- FHIR R4 Provider Directory API conformant with Da Vinci PDex Plan Net
- CMS-0057-F compliance for regulated payer directory publication
- HIPAA-compliant architecture with audit logging for patient-linked queries
- CMS Plan Finder data submission workflow for Medicare Advantage directories

---

## AI-Native Advantage

AI transforms provider directory management from a periodic, manual data-hygiene exercise into a continuous, autonomous verification system. AI agents query licensing boards, DEA, OIG, and NPDB databases in real time to verify credentials without manual follow-up. Machine learning models predict credentialing timelines based on provider type, jurisdiction, and historical patterns -- compressing the industry average from 90-120 days to under 30. NLP-powered directory correction parses unstructured provider data from payer PDFs, provider websites, and clinical notes at 93%+ precision, while network adequacy analytics automatically identify coverage gaps by geography, specialty, and patient demand.

---

## Tech Stack & Deployment

- **Standards:** FHIR R4 with Da Vinci PDex Plan Net and US Core implementation guides; HL7 NDH (National Directory of Healthcare Providers); SMART Scheduling Links for EHR slot discovery
- **Base data layer:** NPPES NPI Registry (public domain, 7M+ active NPIs) with automated weekly refresh from CMS bulk downloads
- **Integrations:** Epic, Oracle Health, athenahealth, and Meditech EHR systems; Availity and clearinghouse eligibility APIs; state licensing board APIs for primary source verification
- **Deployment:** Self-hosted or cloud; HIPAA-compliant architecture required for any patient-linked queries (Business Associate Agreements apply)
- **Regulatory alignment:** ONC 21st Century Cures Act information blocking rules; CMS Interoperability and Patient Access Final Rule; NCQA credentialing accreditation standards

---

## Market Context

The healthcare credentialing software and services market is valued at approximately USD 1.09 billion in 2026, projected to reach USD 2.26 billion by 2035 (Grand View Research, CAGR ~8.5%). The broader payer network management market is projected to grow from USD 4.89 billion to USD 9.72 billion by 2034 (Fortune Business Insights). Enterprise platforms command USD 100K-1M+ annually, while mid-market tools like NexHealth start at USD 299/month. Primary buyers include health system credentialing staff, payer network management teams, medical group administrators, and healthcare IT teams integrating provider data across EHR, billing, and scheduling systems.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context. Note: NPPES NPI data is US government public domain with no licensing restrictions. FHIR standards are W3C-licensed with royalty-free use for conformant implementations.
