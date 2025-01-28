# Schema Overview

This document provides a high-level overview of the SOX/ICFR schemas included in this repository. These schemas aim to support a **top-down** approach, covering everything from entity-level assessments to specific financial statement areas, risks, controls, and remediation.

---

## 1. Entity-Level Schema
- **Filename**: `entityLevel.schema.json`
- **Purpose**: Captures high-level COSO components and entity-level controls.
- **Highlights**:
  - Stores an overall assessment of each COSO component (Control Environment, Risk Assessment, Control Activities, Info & Communication, Monitoring).
  - References entity-level controls (e.g., whistleblower hotline, board oversight).

---

## 2. Financial Statement Area (FSA) Schema
- **Filename**: `fsa.schema.json`
- **Purpose**: Defines financial statement line items or disclosures (e.g., Revenue, Inventory) that are material to SOX/ICFR.
- **Highlights**:
  - Contains relevant assertions (e.g., Existence, Completeness).
  - Tracks inherent vs. residual risk levels.
  - Links to specific Risks via `relatedRisks`.

---

## 3. Process Schema
- **Filename**: `process.schema.json`
- **Purpose**: Describes key business processes (Order to Cash, Procure to Pay), plus sub-processes.
- **Highlights**:
  - Each process has an `owner` and an array of sub-processes with IDs and names.
  - Optionally includes references to external frameworks or internal policies.

---

## 4. Risk Schema
- **Filename**: `risk.schema.json`
- **Purpose**: Represents specific risks that could lead to a misstatement or control failure.
- **Highlights**:
  - Includes `likelihood` and `impact` or risk ratings.
  - References which controls mitigate the risk via `controlIds`.
  - Links to the relevant financial statement area (e.g., `FSA-001`).

---

## 5. Control Schema
- **Filename**: `control.schema.json`
- **Purpose**: Defines both entity-level and process-level controls.
- **Highlights**:
  - `type` (Manual vs. Automated), `frequency` (Monthly, Quarterly, etc.).
  - `assertionsAddressed` links back to FSA or Risk assertions.
  - May reference Information Used in Control (IUC) via `informationUsedIds`.

---

## 6. Control Test (Test Plan) Schema
- **Filename**: `controlTest.schema.json`
- **Purpose**: Details how a control is tested (methodology, frequency, sample size).
- **Highlights**:
  - References a specific Control (`controlId`).
  - Supports separate IUC test attributes to validate data quality.
  - Includes a `status` field for progress tracking.

---

## 7. Information Used in Control (IUC) Schema
- **Filename**: `iuc.schema.json`
- **Purpose**: Specifies the reports, logs, or system data a control relies on.
- **Highlights**:
  - Captures `sourceSystem`, `owner`, and key data fields.
  - Critical for verifying completeness/accuracy of the data used in a control.

---

## 8. Deficiency Schema
- **Filename**: `deficiency.schema.json`
- **Purpose**: Records any control gaps or failures identified during testing.
- **Highlights**:
  - `severity` can be Control Deficiency, Significant Deficiency, or Material Weakness.
  - Links to one or more controls (`controlIds`) found deficient.
  - Points to a Remediation plan via `remediationId`.

---

## 9. Remediation Schema
- **Filename**: `remediation.schema.json`
- **Purpose**: Outlines corrective actions taken to resolve deficiencies.
- **Highlights**:
  - Tracks `dueDate`, `owner`, and `status` (Not Started, In Progress, Completed).
  - References the specific deficiency that prompted the remediation.

---

## 10. User / Role / Permissions Schema (Optional)
- **Filename**: `user.schema.json`
- **Purpose**: Manages user identities, roles, and permissions in a SOX/ICFR tool.
- **Highlights**:
  - Assigns roles (e.g., Control Owner, Reviewer) and permissions (read-only, edit, approve).
  - May integrate with corporate Single Sign-On or other identity systems.

---

## 11. Reference / Meta Schema (Optional)
- **Filename**: `reference.schema.json`
- **Purpose**: Stores references to COSO, PCAOB, or other frameworks.
- **Highlights**:
  - `referenceId` (e.g., “COSO-10”), `title`, `url`.
  - Useful for generating or mapping compliance references.

---

### Relationships at a Glance

- **Entity-Level** → overarching COSO environment.
- **FSA** → identifies material line items, references `relatedRisks`.
- **Risk** → references `controlIds` that mitigate them.
- **Control** → references `informationUsedIds` and addresses certain `assertions`.
- **ControlTest** → links to a specific `controlId`.
- **Deficiency** → ties back to `controlIds`, can point to a `remediationId`.
- **Remediation** → addresses a given deficiency.
- **User/Role** → optional schema to control who has editing or sign-off authority.
- **Reference** → optional external framework references.

---

## Next Steps

- **Review and Customize**: Adjust field names, add or remove properties, or refine `enum` values to align with your organization’s language and risk rating scales.
- **Validation**: Use a JSON Schema validator to ensure each data document conforms to these schemas.

This overview should help new contributors or users quickly understand the purpose and interconnections of each schema.

