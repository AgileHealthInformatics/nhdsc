# National Health Dataset Catalogue: Proposed Reference Specification

A proposed replacement for the requirements specification of Ireland's National Health Dataset Catalogue (nHDsC). It is offered in response to HIQA's *National Health Dataset Catalogue: Requirements and Specifications Report* (HealthData@IE Deliverable 6.1, May 2026), referred to below as **Deliverable 6.1**.

| | |
|---|---|
| **Version** | 0.3, issued for consultation |
| **Date** | 26 October 2026 |
| **Editor** | Dr Tito Castillo, Agile Health Informatics Ltd. |
| **Status** | Unofficial design proposal. Not a publication of HIQA, the Department of Health or any HealthData@IE partner |
| **Published copy** | https://claude.ai/artifact/CRCFLUJdNMCHv3h1xv4RDS |

> **Prepared with generative AI.** This specification was drafted with substantial use of generative AI tools under the editor's direction. See [Provenance and use of generative AI](#provenance-and-use-of-generative-ai) before relying on it.

## Contents

- [What this repository contains](#what-this-repository-contains)
- [Viewing the specification](#viewing-the-specification)
- [Background](#background)
- [Provenance and use of generative AI](#provenance-and-use-of-generative-ai)
- [Critique of Deliverable 6.1](#critique-of-deliverable-61)
- [Drafting choices in the proposed specification](#drafting-choices-in-the-proposed-specification)
- [Decisions left to the owning bodies](#decisions-left-to-the-owning-bodies)
- [Why ReSpec](#why-respec)
- [Limitations](#limitations)
- [Where each Deliverable 6.1 requirement now lives](#where-each-deliverable-61-requirement-now-lives)
- [Sources](#sources)
- [Comments and contributions](#comments-and-contributions)
- [Copyright](#copyright)

## What this repository contains

| File | Purpose |
|---|---|
| `nhdsc-specification-v0-3.html` | The proposed specification, as ReSpec source |
| `README.md` | This file: provenance, rationale and guidance |

A companion *Assurance Report* (Word document) explains the critique and the drafting choices for a non-specialist reader. Most of its content is reproduced below.

## Viewing the specification

The specification is written in [ReSpec](https://respec.org/docs/). The HTML file is a source file: when it is opened in a browser, ReSpec formats it, numbering the sections, building the table of contents, resolving references and drawing the diagrams. This needs an internet connection, because ReSpec and Mermaid (the diagram library) load from public CDNs.

To view it:

- **Online:** use the published copy linked above, which is already formatted.
- **GitHub Pages:** enable Pages for this repository and open the file from the Pages site.
- **Locally:** open the file in an up-to-date desktop browser while online.

A desktop or laptop works best, as some tables are wide.

### Reading the specification

| Marking | Meaning |
|---|---|
| Blue box with an identifier such as `AC-02` | A requirement: one testable statement, with its source and verification method (test, inspection or review) |
| Amber box headed "Policy decision" | A decision for the owning bodies, with options and a proposed default |
| Box headed "Issue" | An open question the specification cannot settle by itself |
| Box headed "Note" | Background; not a requirement |
| `P-nn` in purple | A parameter whose value is still to be set (see the Parameters appendix) |

Requirement identifier prefixes: `BR` business, `IM` information model, `MD` description content, `LC` lifecycle, `QL` quality labels, `CT` contribution, `DS` discovery, `DI` interface with access management, `AC` access and authority, `PB` publication and federation, `NT` notifications, `GV` governance, `AR` architecture, `NF` service qualities, `SE` security and privacy, `AU` audit, `VT` verification. Identifiers are never reused.

## Background

Article 77 of the European Health Data Space (EHDS) regulation, Regulation (EU) 2025/327, requires each Member State's health data access body to publish a public, machine-readable catalogue of the health datasets available for secondary use. Most categories of data must be discoverable by 26 March 2029, and some, including human genetic data, by 26 March 2031. National catalogues feed the EU catalogue under Article 79. Commission Implementing Regulation (EU) 2026/2098, adopted on 18 September 2026, fixes the minimum content of each dataset description, using the HealthDCAT-AP standard.

Deliverable 6.1 sets out HIQA's requirements for Ireland's catalogue. It is a thoughtful, well-researched starting point. However, it contains contradictions, technical errors and gaps that would cause difficulty if it were used to procure and build the catalogue. Many of these arise from how the document is structured rather than from individual sentences, so this proposal rewrites the specification instead of annotating it. It keeps the purpose, scope and stakeholder work of Deliverable 6.1.

## Provenance and use of generative AI

### Tools used

| Tool | Role |
|---|---|
| **Claude** (Anthropic) | Primary drafting tool. Read Deliverable 6.1 and the relevant European sources, drafted the critique, drafted the specification and the Assurance Report, wrote the text, tables and diagrams, and ran the software checks described below |
| **ChatGPT** (OpenAI) | Separate, adversarial reviewer. Produced an initial critique of Deliverable 6.1, used as a starting guide, and then critically reviewed successive drafts of the specification |
| **ReSpec** and **Mermaid** | Open-source tools used to format the specification and draw its diagrams |

### Approach

The work was iterative and directed by the editor throughout.

1. The editor supplied Deliverable 6.1 and set the purpose, audience and scope of each output.
2. Claude analysed Deliverable 6.1, using ChatGPT's initial critique as a guide. Each of ChatGPT's claims was checked against the text of Deliverable 6.1, and external facts were checked against primary sources found by web search, including the piveau supplier documentation, the EHDS regulation and Implementing Regulation (EU) 2026/2098. Claims that could not be verified were removed or marked as unverified. This check corrected several of ChatGPT's points and added many findings it had missed.
3. Claude drafted the specification. The draft was given to ChatGPT for independent critical review, and Claude revised it in response. This cycle was carried out twice. The second review found the remaining issues narrow and correctable; they were addressed in version 0.3, which has not itself been reviewed again. Each review finding was assessed on its merits rather than accepted automatically; one was accepted only in part.
4. Software checks, run by Claude, confirmed the specification's internal structure: that identifiers are unique and every cross-reference points to something that exists. These checks confirm structure, not correctness.
5. The editor directed each stage and made the decisions that are his to make, including output formats, audiences and attribution.

### What this means for readers

- Generative AI can produce text that is fluent but wrong. Both tools are capable of error. Using one to review the other reduces this risk but does not remove it.
- The adversarial reviews were carried out by an AI system, not by human subject-matter experts. **No independent human expert review has yet taken place.**
- None of the controls in the specification has been built or tested in working software.
- Suggested parameter values and the plain-language comparisons are drafting judgements, not evidence.
- Only public documents were used. No personal or confidential data was given to either tool.

The editor takes responsibility for the content, including any errors.

## Critique of Deliverable 6.1

### What Deliverable 6.1 does well

- **Clear legal grounding** in EHDS Articles 51, 77 and 79, the 2029 and 2031 deadlines, and the route to the EU catalogue.
- **Sound method:** a review of European pilot work and three Irish catalogues, and a prototype tested with a cross-sector working group.
- **The key insight:** that the European description format (HealthDCAT-AP) gives no guidance on managing metadata, and that ISO/IEC 11179 addresses this.
- **Reuse rather than build:** adoption of piveau, the open-source platform behind the EU's central health data platform.
- **Care with history:** restoring an earlier description creates a new version rather than overwriting.
- **Honesty about gaps,** marked "to be confirmed" rather than guessed.
- **Accessibility and bilingual delivery** treated as requirements.

### Findings

Severity reflects how likely a problem is to cause failure, delay or rework if Deliverable 6.1 were used to procure and build the catalogue. References such as FR 02 are to Deliverable 6.1.

| ID | Finding | Severity |
|---|---|---|
| F01 | Public access contradicts itself: search is open in one place (FR 02 note) and requires login and administrator approval in others (FR 02, §3.5, §3.6.3, NFR 05) | High |
| F02 | Seven further pairs of requirements contradict each other (see below) | High |
| F03 | No defined stages for a record; nine different status names; no way to send a description back for correction | High |
| F04 | The traceability matrix is misaligned throughout; FR 023 is missing; references point to sections that do not exist | High |
| F05 | Requirements bundle many obligations together and mix legal rules with screen design | Medium |
| F06 | The recommended software platform, piveau, is described incorrectly | Critical |
| F07 | An unrelated commercial product (Pivot-RP) and several other technical errors appear in the design | High |
| F08 | An automated format check (SHACL) is presented as proof of legal compliance | High |
| F09 | The catalogue lists datasets but does not capture what their contents mean | Critical |
| F10 | Four conflicting identifier schemes; dataset identity is fused with organisation and version | High |
| F11 | Quality labels are not enforced, not tied to the data they assess, and their structure is not settled | High |
| F12 | Almost every decision rests with a single IT administrator role | High |
| F13 | Manual entry is the only way to supply descriptions | High |
| F14 | Some catalogue duties in the regulation are not covered | Medium |
| F15 | Basic planning figures are blank while unrelated capacity figures are specified | High |
| F16 | Security and privacy requirements are largely missing | High |
| F17 | Records of approval decisions are not protected like evidence | High |
| F18 | The metadata model is out of date with Implementing Regulation (EU) 2026/2098 | High |
| F19 | The architecture is chosen without comparing options, and includes text from a different system | Medium |
| F20 | No version number, status or change log | Medium |

### Contradictory requirements (F02)

| Topic | One requirement says | Another says |
|---|---|---|
| Export with nothing selected | FR 017: export is disabled | NFR 018: everything visible is exported |
| Approving a deletion | FR 09: System Admin gives final approval | NFR 012: Data Holder Admin confirms; no System Admin step |
| Undoing a deletion | NFR 012 dialog: "cannot be undone" | Same requirement: record is kept and can be restored |
| Datasets compared at once | FR 021: two | NFR 022: up to three |
| Speed of filtering | NFR 017: 0.5 seconds | NFR 021: 2 seconds |
| Review dashboard load | NFR 010: under 2 seconds for 1,000 items | Same requirement: 2 seconds for 200 items |
| Two-factor sign-in | §3.5: central identity service with authenticator apps or security keys | NFR 05: a bespoke form sending codes by email |

### Notes on the main findings

**Public access (F01).** Article 77 requires a publicly available catalogue, so only open access is lawful. A catalogue behind an approved login would exclude patients, journalists, students and many researchers.

**Software platform (F06, F07).** Deliverable 6.1 says piveau Consus publishes records and synchronises them with the EU; according to piveau's documentation, Consus imports and transforms metadata from other sources. It says piveau Hub stores records in Elasticsearch; Hub's principal store is a triplestore, with Elasticsearch as its search index. It relies on a "Piveau Staging" component that does not appear in piveau's published module list. It names Pivot-RP, a commercial research-funding database run by Clarivate, as the component for saved searches. Smaller errors include describing the W3C Data Quality Vocabulary as a "Data Quality Validator" and proposing a log store (Loki) as a substitute for a tracing tool.

**Format checking is not legal checking (F08).** SHACL checks that the right fields are present and correctly formatted. It cannot tell whether a description is true, whether a dataset is correctly classified, or whether a quality label is legally required.

**Meaning of the data (F09).** Two datasets can both state that they record diagnoses in SNOMED CT while using different releases, subsets or local coding rules. Deliverable 6.1 names ISO/IEC 11179 as the relevant standard but specifies nothing that uses it, and its coding-system field records no edition.

**Quality labels (F11).** Article 78(2) of the EHDS requires datasets collected and processed with public funding to carry a data quality and utility label. Deliverable 6.1 does not enforce this, allows a description to be saved without its label when the labelling service is unavailable, and allows "one label per dataset" with no record of which data was assessed. FR 04 lists six areas, matching the six elements in Article 78(3); NFR 07 and FR 021 require scores on "12 dimensions", citing the QUANTUM assessment tool. The report does not say how the two relate.

**Out of date (F18).** Appendix 6 of Deliverable 6.1 copies a field table from an unofficial HealthDCAT-AP draft of December 2023. Implementing Regulation (EU) 2026/2098 now fixes the minimum content in law. This is not a criticism of the authors, who could not have anticipated the final text.

## Drafting choices in the proposed specification

### Design principles

1. **Public by default.** Anything published can be found and read by anyone, without an account.
2. **One authoritative source.** Each piece of information has one owner and one place where it is maintained.
3. **Reference European standards by release.** The schema is defined by Regulation (EU) 2026/2098 and HealthDCAT-AP, and is cited rather than copied.
4. **Decide first, then propagate.** A decision is recorded once, durably, then carried to other systems in a way that can be safely repeated and checked.
5. **Separate deciding from operating.** Those who decide what is published are not those who run the systems.
6. **Every requirement is testable.**

### Main choices

| Choice | What the specification does | Why | Addresses |
|---|---|---|---|
| One testable statement per requirement | Each requirement has its own identifier, source and verification method, grouped by subject | Contradictions become visible and each requirement can be tested alone | F02, F04, F05, F20 |
| Open to everyone | Discovery needs no account (DS-01); registration is self-service (AC-02); one permissions table governs | Article 77 requires a public catalogue | F01 |
| Clear information model | Separates the dataset, description versions, data releases, distributions and quality labels; one persistent IRI per dataset (IM-01, IM-02) | Citations stay valid; labels refer to the data actually assessed | F10 |
| Defined lifecycle | Draft, Awaiting holder approval, Under review, Returned, Approved, Published, Superseded, Withdrawn, Revoked, Discarded; named actors and guards (LC-01, LC-02) | Everyone knows a description's state and who acts next | F03 |
| Text and status separated | Text editable only in Draft; content hash at each hand-over; immutable once approved (IM-03, IM-09, IM-10) | Proves that what was published is what was approved | F03, F17 |
| Four approval guards | G1 structure; G2 required labels present; G3 labels current and applicable; G4 holder attestation and content match. Guards fail closed (LC-08) | Separates kinds of assurance; only G1 can be automated | F08, F11 |
| Decide first, then publish | Decision committed first (PB-01); content staged out of view; a single current-version pointer controls what is public (PB-17, PB-07); notifications wait (PB-18); regular reconciliation | No unapproved content can appear if a system fails part-way | F06, F17 |
| Labels per data release | Five label statuses: Missing, Pending, Verified, Expired, Revoked (QL-14, QL-15); checked for every release on offer (QL-10) | An old label cannot vouch for new data | F11 |
| Access system enforces labels | Catalogue provides label status (DI-01); the access management system must check it at every release decision, on every route (DI-02 to DI-04) | A flag protects nothing unless the receiving system must act on it | F11 |
| Meaning of the data | Coding system and edition required (MD-05); data dictionaries for non-public datasets (MD-06, MD-07) | Makes differences between datasets visible | F09 |
| Two contribution routes | Guided form or harvesting from holders' own catalogues, through the same checks (CT-01 to CT-03) | One authoritative source; no retyping | F13 |
| Deciding separated from operating | Publication authority and service operator; no person holds both (AC-06); named accounts, limited privileged access, break-glass controls (AC-08 to AC-12); named service owner (GV-01) | Content decisions need regulatory standing; technical access can bypass application rules | F12 |
| Correct component responsibilities | Hub stores and serves; Consus harvests; workflow store holds decisions (AR-01 to AR-03); prototype and options appraisal before contract (AR-04, AR-06, AR-07) | Matches supplier documentation; tests the riskiest parts early | F06, F07, F19 |
| Europe and single information point | Federation with status, retries, escalation and proof of match (PB-02 to PB-05, PB-13 to PB-16) | Differences must be resolved, not just reported | F14 |
| Obligations and trusted holders | Register of each holder's Article 51 obligations (IM-06, IM-07); trusted-holder marking (MD-13) | Shows what is still missing before the deadlines | F14 |
| Service quality, security, privacy | Targets derive from set planning figures (NF-01); recovery by information class (NF-05); security and DPIA (SE-01 to SE-05); minimal logging (SE-06, SE-08); disclosure controls (MD-10, MD-11, MD-14, MD-18, DS-11) | Testable targets; proportionate protection; data minimisation | F15, F16 |
| Audit evidence | Append-only, integrity-protected decision records, separate from operational logs (AU-01 to AU-06) | Shows who approved what, and on what evidence | F17 |
| Screen design out of scope | Button wording, layouts and similar details move to design guidance | Keeps the specification about obligations | F05 |
| Verification | Executable tests, including deliberate failure tests and checks of what the public actually sees (VT-01 to VT-05) | Proves the safeguards work | — |

## Decisions left to the owning bodies

| Ref | Decision | Proposed approach |
|---|---|---|
| PD-01 | Whether a dataset that legally needs a quality label may be listed before its label is complete | Option B: list with label Pending; withhold data release until verified, within a time limit. Requires DI-02 to DI-04 in the access system's contract. Legal advice required |
| PD-02 | Which body holds publication authority | The health data access body; relationship to HIQA, the HSE and the HRB to be settled |
| PD-03 | Internal structure of the quality label | As set by the Article 78(6) implementing act, with QUANTUM scores mapped to it |
| PD-04 | Whether to establish a national register of data definitions | Open; the catalogue links to holders' data dictionaries meanwhile |
| PD-05 | Who sets each planning parameter | Each parameter names who decides it |
| GV-01 | Who is the single service owner | To be named before procurement |

The specification also lists 23 parameters (P-01 to P-23), each classed as capacity, service level, governance, architecture or configuration. Suggested values are starting points for discussion. Capacity, service-level and governance parameters must be settled before the specification is used as an implementation baseline.

## Why ReSpec

ReSpec is a free tool used by the W3C and other standards bodies to write technical specifications. It was chosen over a word-processed document because:

1. **It matches the European standards the catalogue depends on.** HealthDCAT-AP and its parent standards are published in this style.
2. **Every requirement has a permanent link,** such as `#LC-04`, which test plans, supplier responses and minutes can cite.
3. **It separates firm rules from open questions,** using distinct, consistent markings.
4. **It is easier to keep accurate.** References are listed once and linked automatically, and the plain-text source can be kept under version control, as in this repository.
5. **It can be processed by software.** Requirements are marked up individually and can be extracted into test plans or trackers.

The main drawback is that some readers are more comfortable with Word. The formatted page can be saved or printed to PDF from a browser.

## Limitations

- **It is a design, not a working system.** VT-01 to VT-05 set out the tests needed.
- **Legal advice is needed** on PD-01 before a choice is made.
- **No independent human expert review has yet taken place.** One is recommended before the specification is used for procurement, covering clinical, data, technical, security and legal expertise.
- **Suggested values are starting points,** not drawn from any source.
- **European standards continue to evolve.** Each new HealthDCAT-AP release will need an impact assessment (MD-04).

## Where each Deliverable 6.1 requirement now lives

| Deliverable 6.1 | Title | Proposed specification | Change |
|---|---|---|---|
| BR 01 | Metadata record creation | BR-01 | Retained |
| BR 02 | Publication and update | BR-02 | Retained |
| BR 03 | Searching for datasets | BR-03 | Corrected (F01) |
| — | (new) | BR-04 to BR-06 | Added (F14) |
| FR 01 | Multilingual support | MD-12, NF-08, NF-12 | Retained |
| FR 02 | Identification and authorisation | DS-01, AC-01 to AC-12 | Corrected (F01, F12, F16) |
| FR 03 | Create and edit descriptions | CT-01 to CT-07, IM-06, MD-06, MD-08 to MD-11, MD-15 | Corrected (F13, F14, F16) |
| FR 04 | Quality and utility labels | QL-01 to QL-07, QL-13 to QL-15 | Corrected (F11) |
| FR 05 | Enforce minimum elements | MD-01, MD-17, CT-05, guard G1 | Corrected (F18) |
| FR 06 | Submit description | LC-02 (submit), NT-01 | Retained |
| FR 07 | Review description and labels | LC-02 (return, revoke), QL-05 | Corrected (F03) |
| FR 08 | Publish description | LC-02 (approve), PB-01, PB-08, PB-17, IM-01, IM-02, IM-11, MD-09, MD-14 | Corrected (F10) |
| FR 09 | Update or delete; change history | IM-03, IM-10, LC-02 (withdraw, discard), LC-03 | Corrected (F02, F03) |
| FR 010 | Versioning | IM-04, IM-05, IM-08, IM-09 | Retained |
| FR 011 | Rollback | LC-04 | Retained, simplified |
| FR 012 | Periodic reviews | LC-05, LC-06, LC-10 | Retained |
| FR 013 | Review reminders | NT-02, NT-04 | Retained |
| FR 014 | Audit trails | AU-01, AU-02, AU-05, AU-06 | Corrected (F17) |
| FR 015 | Export audit trail | AU-04 | Retained |
| FR 016 | Search | DS-01, DS-02 | Corrected (F01) |
| FR 017 | Select and export | DS-05 | Corrected (F02) |
| FR 018 | Save and share searches | DS-06, DS-07 | Corrected (F07) |
| FR 019 | Alerts on saved items | DS-13, NT-03 | Retained |
| FR 020 | Filter and sort | DS-03, DS-12 | Retained |
| FR 021 | Compare datasets | DS-04 | Corrected (F02) |
| FR 022 | Feedback | DS-08 | Corrected (F02) |
| FR 023 | Dataset basket | DS-09; DI-01 to DI-04 | Deferred, now traced (F04) |
| NFR 01–02 | Browsers and mobile | NF-07, NF-09 | Retained; screen detail moved to design guidance |
| NFR 03 | Multilingual | NF-08, NF-12 | Retained |
| NFR 04 | Footer | Design guidance | Moved (F05) |
| NFR 05 | Sign-in and registration | AC-02 to AC-04, AC-10 | Corrected (F01, F16) |
| NFR 06–014 | Record management qualities | LC, IM and PB requirements; NF-03 | Corrected (F02, F03, F15) |
| NFR 015 | Reviews, notifications, audit | LC-05, LC-06, NT-02, AU requirements | Corrected (F17) |
| NFR 016 | Audit export | AU-04 | Retained |
| NFR 017–023 | Discovery qualities | DS requirements, NF-02, SE-06, SE-08 | Corrected (F02, F15, F16) |
| NFR 024 | Backup, load, hosting, recovery | NF-01, NF-04 to NF-06, NF-10, NF-11, NF-13, SE-07, parameters | Corrected (F15) |
| §3.4–3.6 | Technical specification | AR-01 to AR-07 | Corrected (F06, F07, F19) |
| Appendix 6 | Metadata field table | MD-01 to MD-04, MD-17 (by reference to EU law) | Replaced (F18) |

## Sources

- HIQA, *National Health Dataset Catalogue: Requirements and Specifications Report*, HealthData@IE Deliverable 6.1, May 2026.
- [Regulation (EU) 2025/327 on the European Health Data Space](https://eur-lex.europa.eu/eli/reg/2025/327/oj), in particular Articles 51, 60, 77, 78 and 79.
- Commission Implementing Regulation (EU) 2026/2098 of 18 September 2026 on minimum metadata elements for dataset descriptions under Article 77(4).
- [HealthDCAT-AP specification](https://healthdataeu.pages.code.europa.eu/healthdcat-ap/releases/latest/).
- [piveau solution description](https://interoperable-europe.ec.europa.eu/eu-oss-catalogue/solutions/piveau), Interoperable Europe, and [piveau documentation](https://doc.piveau.eu/general/quick-start/).
- [W3C Data Catalog Vocabulary (DCAT) Version 3](https://www.w3.org/TR/vocab-dcat-3/).
- [Regulation (EU) 2022/868, the Data Governance Act](https://eur-lex.europa.eu/eli/reg/2022/868/oj).
- ISO/IEC 11179, Metadata registries.

## Comments and contributions

Comments are welcome as GitHub issues. Please cite the requirement identifier (for example `AC-02`) or section, say whether the requirement is right, wrong or missing, and explain why. Proposed changes to the specification are recorded in its change log.

## Copyright

Copyright © 2026 Agile Health Informatics Ltd.
