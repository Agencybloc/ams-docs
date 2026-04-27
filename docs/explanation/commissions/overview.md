---
title: Commissions overview
area: commissions
status: live
owner: commissions-team
last_verified: 2026-04-27
sources: []
---

# Commissions overview

Commissions are payments made by carriers to agents when a policy is sold, renewed, or maintained. AMS+ tracks every commission from carrier payment through distribution to individual agents.

This page explains the structure of how commissions work in AMS+. For calculation details, see [How commission splits are calculated](how-it-works.md).

---

## What AMS+ tracks

AMS+ records commissions at two levels:

**Carrier payments** — the raw amount received from the carrier for a policy. These are imported via carrier statement uploads or entered manually.

**Agent distributions** — the portion of each carrier payment that flows to each agent in the policy's hierarchy. Calculated automatically from the split rules on the policy.

## Commission types

| Type | When it's paid | Typical rate |
|---|---|---|
| New business | When a new policy is issued | Higher — incentivizes growth |
| Renewal | When an existing policy renews | Lower than new business |
| Override | Paid to an upline agent on their downline's production | Percentage of the downline's commission |
| Bonus | Carrier-specific production bonuses | Varies widely |

## When commissions are calculated

Commissions are calculated when a carrier payment is recorded against a policy. The platform matches the payment to the policy, looks up the active splits, and creates distribution records for each agent.

If the policy has no splits defined, the payment is held in **pending** status until splits are entered.

---

## Why this matters

Accurate commission tracking is the core function most agencies rely on AMS+ for. Errors in commissions directly affect agent income and agency cash flow.

## Related pages

- [How commission splits are calculated](how-it-works.md)
- [Commission reconciliation](reconciliation.md)
- [Record types reference](../../reference/record-types/index.md)
