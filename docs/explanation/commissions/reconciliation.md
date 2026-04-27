---
title: Commission reconciliation
area: commissions
status: live
owner: commissions-team
last_verified: 2026-04-27
sources: []
---

# Commission reconciliation

Reconciliation is the process of verifying that the commissions recorded in AMS+ match the amounts received from carriers. Discrepancies — amounts that don't match or policies without a corresponding payment — are surfaced as reconciliation exceptions.

---

## How reconciliation works

Carriers send commission statements on a schedule (typically monthly). Agencies upload these statements into AMS+, and the platform matches each line to a policy and agent.

**Matched lines** — the carrier paid the expected amount for a known policy. These close automatically.

**Unmatched lines** — the carrier paid for a policy AMS+ doesn't recognize, or paid a different amount than expected. These require manual review.

**Missing lines** — AMS+ expected a payment (based on the policy's renewal schedule) but none appeared on the statement. These generate a follow-up alert.

## Common reconciliation exceptions

| Exception | Typical cause |
|---|---|
| Amount mismatch | Rate change not yet reflected in AMS+; chargeback applied |
| Unrecognized policy | Policy number entered incorrectly; carrier issued new number |
| Missing payment | Policy lapsed at carrier; statement delivery delay |
| Duplicate payment | Carrier re-sent a prior statement; import run twice |

## Resolving exceptions

For each exception, the agency can:
- **Match manually** — link the exception to the correct policy.
- **Create an adjustment** — record the difference as an adjustment for audit purposes.
- **Mark as waived** — acknowledge the discrepancy without creating an adjustment (for small rounding differences).

All resolutions are logged with the resolving user and timestamp.

---

## Why this matters

Unreconciled commissions mean agents may not be paid correctly — or the agency may be leaving carrier money unclaimed.

## Related pages

- [Commissions overview](overview.md)
- [How commission splits are calculated](how-it-works.md)
