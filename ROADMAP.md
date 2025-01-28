# Project Roadmap

This document outlines the major milestones, features, and enhancements planned for our SOX/ICFR open-source schema project. Our goal is to evolve these schemas from a useful **initial draft** into a **fully mature** and **industry-accepted** framework for documenting internal controls, risks, and compliance data.

---

## Overview

- **Current Status (Phase 1)**: Core schemas drafted (Risk, Control, IUC, Deficiency, etc.) and basic documentation (Usage Guide, FAQ, COSO/PCAOB Mapping).
- **Target Outcome**: A robust, flexible, and well-documented schema set that auditors, compliance officers, and finance teams can easily implement across tools and systems.

---

## Milestones & Phases

### Phase 1: **Initial Release** (Completed)
- **Scope**:
  - Drafted JSON Schemas for key ICFR objects: EntityLevel, Risk, Control, ControlTest, Deficiency, Remediation, IUC.
  - Provided basic documentation: README, Schema Overview, Usage Guide, FAQ, and COSO/PCAOB Mapping.
  - Included sample JSON files in the `examples/` directory.
- **Status**: **Complete**. We’ve established the foundational schema and documentation.

### Phase 2: **Community Feedback & Adoption** (In Progress)
- **Objectives**:
  - Gather **feedback** from early adopters (internal auditors, GRC professionals, open-source contributors).
  - Refine schema fields, naming conventions, and enumerations based on real-world use cases.
  - Increase **test coverage** for example JSON documents (validate them in CI).
  - Explore **user management** fields for expanded collaboration (e.g., more robust `user.schema.json`).
- **Timeline**: Q1–Q2 next year.
- **Success Criteria**:
  - At least **5+ organizations** or individuals successfully using or piloting the schemas.
  - **Pull requests** from the community that enhance the schema or fix issues.
  - Updated **CHANGELOG.md** reflecting active iteration.

### Phase 3: **Validation & Integration Tools** (Upcoming)
- **Objectives**:
  1. **Automated Validation**: Implement GitHub Actions or other CI pipelines that automatically validate new/updated JSON documents against the schemas.
  2. **Reference Data & Tools**: Possibly create a small library (in Node.js/Python) that helps users **generate** or **parse** the schema documents (risk → control → deficiency chain).
  3. **Extended Examples**: Add more realistic data sets (multiple processes, multiple years, entity-level with sub-entities).
- **Timeline**: Q3 next year.
- **Success Criteria**:
  - Automated tests pass on all schema changes, ensuring **backward compatibility** or indicating **breaking changes**.
  - Clear instructions on how to **integrate** these schemas with popular GRC or analytics platforms.

### Phase 4: **Advanced Features & AI Integration**
- **Objectives**:
  1. **AI-Ready Data**: Add optional fields or references that support advanced analytics (e.g., risk scoring models, machine learning predictions).
  2. **Cross-Schema Linking**: Ensure easy navigation from one object to another (e.g., a deficiency to the underlying risk, the root cause of that risk, etc.).
  3. **Versioning & History**: Introduce best practices for version control of each object over time (e.g., “Control v1.0” vs. “v2.0”).
- **Timeline**: Q4 next year–Q1 the following year.
- **Success Criteria**:
  - **Pilot AI modules** that parse these JSON schemas to suggest risk priorities or identify incomplete dependencies.
  - Clear guidelines on how to store **historical changes** for auditing or retrospective analysis.
  - Possibly a basic **graph-based** or **knowledge-graph** demonstration for multi-hop relationships (Risk → Control → IUC → Deficiency).

### Phase 5: **Mature Standard & Wider Ecosystem**
- **Objectives**:
  1. **Industry Recognition**: Present or share these schemas with broader audit and compliance communities (e.g., IIA, ISACA, or Big 4 advisory).
  2. **Tool Integrations**: Provide ready-to-use **plugins or connectors** for common GRC tools (e.g., ServiceNow GRC, SAP GRC) or open-source solutions.
  3. **Community Governance**: Form a small maintainers committee or working group that oversees schema evolution, versioning, and alignment with new regulatory guidance.
- **Timeline**: Ongoing, after we solidify the above phases.
- **Success Criteria**:
  - Partnerships or endorsements from recognized **audit** or **compliance** bodies.
  - Widespread use in at least **10+** organizations, with **community-driven** enhancements.
  - A stable **major version** (e.g., `v1.x` or `v2.x`) that’s widely accepted as the reference standard.

---

## Versioning Strategy

We plan to use **semantic versioning**:

- **MAJOR**: Breaking changes (field removals or renames, structural overhauls).  
- **MINOR**: Backward-compatible additions (new optional fields, new schemas).  
- **PATCH**: Bug fixes, minor clarifications in documentation or enumerations.

We will maintain older versions in separate folders (`schemas/v1`, `schemas/v2`) to help teams transition gradually.

---

## How You Can Help

1. **Try It Out**: Deploy the schemas in a test environment or pilot within your organization.  
2. **Open Issues**: Let us know if you find gaps, inconsistent naming, or missing fields for your scenario.  
3. **Submit Pull Requests**: Contribute new fields, improved docs, or bug fixes.  
4. **Spread the Word**: If this approach helped you streamline your SOX/ICFR documentation, share it with colleagues or on social media.

---

## Contact & Feedback

- **GitHub Issues**: Use [Issues](../../issues) to report bugs or request features.
- **Discussions**: Start a discussion if you have a broad question or want to propose a major feature.
- **Maintainers**: You can also email the maintainers directly (see [README.md](../README.md) for contact info).

**Together, we can make this an industry-leading open framework** for documenting and managing SOX/ICFR requirements!

