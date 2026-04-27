---
title: "Voice example: How-to page"
status: internal
---

# How to resolve an E&O compliance alert

E&O alerts appear when a policy is missing required information before its effective date. This guide walks you through resolving the most common alert types.

---

## Before you start

You'll need:
- Access to the policy record in AMS+
- The carrier's requirements document (available in the Carrier Library)
- Edit permissions on the policy (ask your agency admin if you don't have these)

---

## Step 1: Open the alert

From the **Compliance** dashboard, click the alert. The alert panel shows:
- Which policy triggered it
- Which field is missing or invalid
- The deadline (usually the policy's effective date minus a buffer set by the carrier)

## Step 2: Identify the missing information

The alert panel links directly to the policy record. Open it. The missing field is highlighted in red.

Common missing fields:

| Alert type | Usually means |
|---|---|
| Missing beneficiary | The policy has no primary beneficiary on file |
| E&O expiry | The writing agent's E&O policy expired |
| Missing NPN | The agent's National Producer Number wasn't saved |
| Address mismatch | Client's mailing address doesn't match the carrier's records |

## Step 3: Correct the record

Edit the policy and fill in the required field. For **E&O expiry** alerts, update the agent record instead — the policy record will clear automatically once the agent's E&O is current.

!!! warning "Don't mark the alert resolved manually"
    The alert closes automatically when the missing data is saved. If you manually close it without fixing the underlying issue, the carrier may still reject the policy.

## Step 4: Verify the alert cleared

Return to the Compliance dashboard. The alert should no longer appear. If it does, wait 60 seconds and refresh — the compliance check runs asynchronously.

If the alert persists after 5 minutes, contact support with the policy number and alert ID.

---

## Why this matters

Unresolved E&O alerts can delay policy activation and in some cases result in carrier rejection. Resolving them promptly protects both the client's coverage and the agency's carrier relationship.

## Related pages

- [E&O compliance overview](../explanation/compliance/overview.md)
- [Carrier requirements reference](../reference/record-types/carrier.md)
