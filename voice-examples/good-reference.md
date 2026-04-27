---
title: "Voice example: Reference page"
status: internal
---

# Policy record fields

Every policy in AMS+ is a record with a defined set of fields. This page describes each field, what it means, and where the value comes from.

---

## Identity fields

| Field | Description | Set by |
|---|---|---|
| Policy number | Carrier-assigned identifier. Unique within a carrier. | Carrier or manual entry |
| Internal ID | AMS+ system ID. Stable; never reused. | System |
| Type | Product type (Medicare Advantage, Life, P&C, etc.) | Agent at policy creation |
| Status | Current lifecycle state. See [Policy lifecycle](../explanation/policies/overview.md). | System (based on events) |

## Coverage fields

| Field | Description | Notes |
|---|---|---|
| Effective date | Date coverage begins. | Required before policy can go active. |
| Termination date | Date coverage ends. Empty if still active. | |
| Renewal date | When the next renewal is due. | Calculated from effective date + term. |
| Coverage amount | Face value (life policies) or annual premium (health). | Carrier-defined; used in commission calculations. |

## Agent and hierarchy fields

| Field | Description | Notes |
|---|---|---|
| Writing agent | The agent who sold the policy. | Required. |
| Hierarchy | The commission split tree. | Defaults to the writing agent's hierarchy default. |
| Splits | Percentages by agent. Must sum to 100%. | See [Commission splits](../explanation/commissions/how-it-works.md). |

## Compliance fields

| Field | Description | Notes |
|---|---|---|
| Beneficiary | Primary beneficiary name and relationship. | Required by most carriers before activation. |
| HIPAA consent | Whether the client has signed a HIPAA consent form. | Required for health policies. |
| E&O verified | Whether the writing agent's E&O is current at effective date. | Checked automatically against agent record. |

---

## Why this matters

Knowing what each field does prevents data-entry errors that trigger compliance alerts or delay commission payments.

## Related pages

- [How E&O compliance alerts work](../how-to/resolve-eo-alert.md)
- [How commission splits are calculated](../explanation/commissions/how-it-works.md)
- [Policy lifecycle](../explanation/policies/overview.md)
