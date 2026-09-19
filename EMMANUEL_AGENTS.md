# Emmanuel Agents

This branch is Emmanuel's curated layer on top of `msitarzewski/agency-agents`.

## Purpose

Keep the upstream agent library intact while installing and customizing only the small team used across Lensora, PostPatch, ReplaceIt, client work, and future projects.

## Approved Core Team

| Role | Source file | Use |
| --- | --- | --- |
| Product Manager | `product/product-manager.md` | Scope, requirements, product decisions |
| Frontend Developer | `engineering/engineering-frontend-developer.md` | React UI implementation |
| Backend Architect | `engineering/engineering-backend-architect.md` | Firebase/backend architecture and data flows |
| Minimal Change Engineer | `engineering/engineering-minimal-change-engineer.md` | Smallest safe diff; prevents scope creep |
| Code Reviewer | `engineering/engineering-code-reviewer.md` | Independent code review |
| Reality Checker | `testing/testing-reality-checker.md` | Verify claims against actual evidence |
| SEO Specialist | `marketing/marketing-seo-specialist.md` | SEO work, especially ReplaceIt and content products |
| Tracking Specialist | `paid-media/paid-media-tracking-specialist.md` | GTM, GA4, Meta, conversion and tracking work |

## Workflow

Use only the agents needed for the task.

Typical product feature:

`Emmanuel approval -> Product Manager -> Builder -> Code Reviewer -> Reality Checker -> Emmanuel review`

For small fixes:

`Emmanuel approval -> Minimal Change Engineer -> Code Reviewer -> Reality Checker`

For SEO:

`Emmanuel approval -> SEO Specialist -> Builder if code is required -> Reality Checker`

For tracking:

`Emmanuel approval -> Tracking Specialist -> Builder if code is required -> Reality Checker`

## Authority Rules

1. Emmanuel makes final product and implementation decisions.
2. Project documentation and approved project rules are the source of truth.
3. Agents must not invent product requirements or override approved project decisions.
4. Do not expand scope without explicit approval.
5. Do not design or redesign unless the task asks for design work.
6. React is the default frontend and Firebase is the default backend unless a project explicitly says otherwise.
7. Preserve existing working behavior unless a requested change requires otherwise.
8. Prefer minimum viable diffs over broad refactors.
9. Copywriting is handled through Emmanuel's approved Notion copywriting workflow, not generic agent copy.
10. Use these execution states consistently:
   - **PLANNING ONLY** — nothing live changed.
   - **READY FOR GO** — implementation is approved but not executed.
   - **EXECUTED LIVE** — repository/site state actually changed.

## Codex Installation

After cloning this repo locally and checking out `emmanuel-agents`:

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex --agent product-manager,frontend-developer,backend-architect,minimal-change-engineer,code-reviewer,reality-checker,seo-specialist,tracking-specialist
```

The installed Codex agents live globally under:

```text
~/.codex/agents/
```

They can then be used from Lensora, PostPatch, ReplaceIt, or any other project without copying this repository into each project.

## Branch Policy

- `main` stays close to upstream.
- `emmanuel-agents` contains Emmanuel-specific curation and customizations.
- Pull upstream improvements into `main`, then selectively merge useful changes into `emmanuel-agents`.
- Customize only agents that are actively useful.
