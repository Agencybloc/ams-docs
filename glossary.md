# AMS+ Glossary

Domain vocabulary for AgencyBloc AMS+. Loaded as a cached prompt prefix by the docs orchestrator.

Use these terms consistently across all documentation. When a term appears for the first time on a page, link to its entry here.

---

## Agent

An insurance agent or broker who sells and services policies through AMS+. Not to be confused with an AI agent (always qualified as "AI agent" or "docs agent" in this documentation).

## Agency

The business entity that employs or contracts agents. An agency may have a hierarchical structure with a managing agent at the top and downline agents below.

## Business area

A functional domain within AMS+ (e.g., commissions, policies, compliance). Determines code ownership, docs ownership, and Jira project routing. Defined in `taxonomy.yml`.

## Carrier

An insurance company that issues policies. Also called the "insurance carrier" or "insurer." Carriers are configured in AMS+ with their commission schedules and product lines.

## Commission

Money paid by a carrier to an agent or agency when a policy is sold, renewed, or maintained. Commissions can be split across a hierarchy of agents.

## Commission split

The rule that distributes a commission among multiple agents in a hierarchy. Splits are defined as percentages that must sum to 100%.

## ConfigCat

The feature-flag platform used by AgencyBloc to control which features are live in which environments. The docs pipeline reads ConfigCat state to determine whether to document a feature as live or pending.

## Downline agent

An agent who sits below another agent in the commission hierarchy. Downline agents receive a portion of commissions earned on policies they manage.

## E&O

Errors & Omissions — professional liability insurance for agents. AMS+ enforces E&O compliance requirements before policies reach certain states.

## Effective date

The date on which a policy's coverage begins. Many compliance rules are evaluated relative to the effective date.

## Feature flag

A ConfigCat-managed toggle that enables or disables a feature in a specific environment. The docs pipeline uses flag state to determine the `status` frontmatter on docs pages.

## Hierarchy

The tree structure of agents and agencies within an account. Commissions flow up the hierarchy; downline agents report to upline agents.

## Policy

An insurance contract between a carrier and a client, managed through AMS+. Policies have a lifecycle (quoting → submitted → active → lapsed/terminated).

## Policy lifecycle

The sequence of states a policy moves through from quoting to termination. Each state transition may trigger compliance checks, commission calculations, and notifications.

## Reconciliation

The process of verifying that commissions recorded in AMS+ match amounts received from the carrier. Discrepancies trigger alerts for the agency to investigate.

## Renewal

When an existing policy is extended for another term. Renewals may trigger new commission payments and require updated compliance verification.

## Upline agent

An agent who sits above another agent in the commission hierarchy. Upline agents receive an override on commissions earned by their downline.
