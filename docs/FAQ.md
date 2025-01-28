# Frequently Asked Questions (FAQ)

Below are common questions about this SOX/ICFR schema repository, along with answers and tips.

---

## 1. Why JSON Schemas Instead of XBRL or XML?

- **Simplicity & Popularity**: JSON is widely used in modern web and backend applications, making it easy to adopt.
- **Flexibility**: JSON Schema allows optional fields and quick iteration if requirements change.
- If needed, you can **convert** JSON to XBRL or XML formats for external reporting.

---

## 2. Do I Have to Store the Data as JSON in My Database?

- **No**. You can store the same information in relational tables or a graph database. The JSON schemas are primarily for **standardized interchange** and **validation**.
- Many teams keep a relational model internally but **export** or **import** data as JSON for easy sharing or API usage.

---

## 3. Are the Risk/Impact Ratings Fixed (High, Medium, Low)?

- **They’re placeholders** in the schema’s `enum` fields. Feel free to replace with numeric scales or alternate wording like “Low, Moderate, High” or “1-5”.

---

## 4. How Do I Handle Versioning of Controls or Risks Over Time?

- You can add fields like `version` or `effectiveDate` to each schema object if you need to track historical changes. Alternatively, manage version control in your **Git** or database.
- Some organizations store old versions in a “history” collection or table, while the current version remains “active.”

---

## 5. What If I Have an Unusual Use Case Not Covered Here?

- You can **extend** the schemas with additional optional fields. For instance, add a `customAttributes` object for extra metadata.
- The schemas are deliberately flexible so you can adapt them to unique processes or local requirements.

---

## 6. How Do I Map These Schemas to My Existing GRC Tool?

- Many GRC tools allow **imports** from CSV or APIs. You can create a script that **transforms** your JSON data to the tool’s required format.
- Conversely, you can **export** data from a GRC tool and format it as JSON to validate against these schemas.

---

## 7. Is This Repository Officially Endorsed by a Regulatory Body?

- **No**, it’s an open-source community-driven effort. It’s aligned with widely recognized frameworks (COSO, PCAOB) but **not** an official requirement from any regulator.
- However, auditors often appreciate structured data that clearly shows the top-down risk and control mapping.

---

## 8. How Do I Contribute or Suggest Changes?

- We welcome pull requests for new fields, corrections, or improvements to documentation. See our [CONTRIBUTING.md](../CONTRIBUTING.md) for details.
- You can also open an **issue** if you encounter a bug or need a feature.

---

## 9. Can I Use This Schema for Non-SOX Internal Controls?

- **Yes**. The concepts of “risk,” “control,” and “deficiency/remediation” apply broadly to other compliance frameworks. You might just rename or adjust fields to match your domain.

---

## 10. What About Data Security and Access Control?

- These schemas define **content** and **relationships**. Actual security controls (encryption, database permissions) must be handled in your application or infrastructure layer.
- If using sensitive data (e.g., user permissions, financial amounts), ensure you have **robust** access restrictions, encryption, and audit logging in place.

---

## 11. Where Can I Learn More About COSO and PCAOB Standards?

- **COSO**: Visit [www.coso.org](https://www.coso.org) for official frameworks, including the 2013 and 2017 updates.
- **PCAOB**: See [pcaobus.org](https://pcaobus.org) for Auditing Standard (AS) 2201 (formerly AS5), which covers internal control audits.

If you have further questions not answered here, feel free to open a discussion or issue in this repository!

