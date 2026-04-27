# AMS+ Docs Style Guide

This guide applies to all content in this repository. The AI pipeline loads it as a cached prompt prefix on every run. Human editors should internalize it.

---

## Audience

**Primary:** Product managers, support agents, onboarding coordinators, and agency owners using AMS+. Most are not engineers. Many have deep insurance-domain knowledge but no code literacy.

**Secondary:** New engineers orienting to AMS+ business rules. They need the *why*, not the *how*.

Write for the primary audience by default. If a section is engineering-specific, call it out explicitly and consider whether it belongs in a separate doc.

---

## Voice

**Direct.** State the behavior, then the reason. Not "it is important to note that commissions may be split..." — just "AMS+ splits commissions when..."

**Concrete.** Use real-world scenarios. An agency receiving a renewal commission from Humana is more useful than "an entity receiving a payment event."

**Present tense.** Describe how the feature works now, not how it was built. Exception: feature-flagged features not yet live use future tense ("When this is enabled...").

**Second person for how-to.** "Click Save. AMS+ creates the record." Not "The user clicks Save. The system creates the record."

---

## Formatting

### Headings

- H1: page title only (in frontmatter, not body)
- H2: major sections
- H3: subsections within a section
- No H4 or deeper — restructure instead

### Lists

- Use bullet lists for unordered items with 3+ members
- Use numbered lists only for sequential steps
- No nested lists deeper than 2 levels

### Tables

Use tables for reference data: field definitions, status values, flag states. Not for prose explanation.

### Code and UI elements

- Wrap field names, button labels, and menu paths in **bold**: **Save**, **Commission Rate**, **Policies > Renewals**
- Wrap flag keys in backticks: `new-commission-splits-v2`
- Never paste raw C# or SQL — link to developer docs instead

### Callouts

Use MkDocs Material admonitions sparingly:

```
!!! note
    Use for important but non-blocking context.

!!! warning
    Use only for behavior that surprises users or can cause data issues.

!!! info "Coming soon"
    Use for pending-flag content.
```

---

## Diagrams

- Use Mermaid for flowcharts and state machines
- Maximum 10 nodes per diagram
- Label every arrow
- Add alt text as a paragraph after the diagram block summarizing what it shows

---

## Page structure

Every page follows this structure:

1. **Frontmatter** (see `CLAUDE.md` for schema)
2. **Opening paragraph** — one or two sentences answering "what is this and why does it exist?"
3. **Body** — organized by H2 sections appropriate to the Diátaxis type
4. **Why this matters** — one sentence, H2 heading
5. **Related pages** — bullet list, max 5 links, H2 heading

---

## Terminology

Use terms from `glossary.md` consistently. When in doubt, use the glossary definition. If a term is missing, add it to the glossary first, then use it.

**Always use:**
- "AMS+" not "the system," "the platform," or "the app"
- "agency" not "client" (unless referring to the client record specifically)
- "carrier" not "insurance company"
- "downline" not "sub-agent" or "child agent"
- "renewal" not "re-enrollment" unless CMS uses that term in a specific context

**Never use:**
- Implementation details: class names, method names, database table names
- Jargon without a glossary entry

---

## Citations

Every substantive claim about a business rule must cite its source as a markdown footnote:

```markdown
Commissions are split based on the hierarchy active at the *policy effective date*, not the payment date.[^1]

[^1]: AMS-4521, implemented in MonolithCommissions#892.
```

The orchestrator post-processes footnotes into the `sources` frontmatter block. Do not manually edit the `sources` block.

---

## Feature-flagged content

If behavior is behind a ConfigCat flag:

- Set `status: pending-flag` in frontmatter
- Write in future tense: "When this is enabled, AMS+ will..."
- Add an admonition at the top of the section:
  ```
  !!! info "Coming soon"
      This feature is currently in testing and not yet available to all agencies.
  ```
- Do not describe gated behavior as current reality

---

## What triggers a doc update

A doc page should be updated when:
- A business rule changes
- A feature is added, changed, or removed
- A feature-flag state transitions (gated → partial → live)
- A term in the glossary is renamed

A doc page does NOT need updating for:
- Pure refactors with no behavior change
- Dependency bumps
- Test-only changes
- Infrastructure changes with no user-visible effect
