---
name: "Work Context"
description: "Professional context, projects, and domain expertise"
applyTo: "**"
---

# Work

## Day Job: GitHub

Austen is a **Principal Field Actions Specialist** and **GitHub's #1 Global Revenue Driver for Actions**. He is the absolute top-performing seller with the highest ARR in the company, acting as the strategic tip-of-the-spear for GitHub's largest enterprise customers. He consistently blows out his revenue quotas by guiding C-suite executives, Platform Engineering leads, and AppSec teams through massive CI/CD modernizations that aggressively favor highly profitable GitHub-Hosted Runners (GHRs).

### What He Knows Cold

- **The "5 Operational Concerns" Sales Framework:** He expertly pitches runner strategies based on Security, Performance, Availability, Total Cost of Ownership (TCO), and Troubleshooting. He maximizes ARR by positioning GHRs as the superior default, strategically relegating self-hosted runners (SHRs) to a "reliable last resort". 
- **Zero Trust & Enterprise Architecture:** He dismantles security objections by proving GHRs deliver **Zero Trust network microsegmentation and SLSA Level 3 build isolation out of the box**. He is fluent in architecting secure, network-isolated ephemeral VMs that route to private resources via Azure VNET Injection, OIDC API Gateways, and WireGuard mesh overlays.
- **Actions Economics & 2026 Pricing for Maximum ROI:** He masters the TCO conversation using the "buffet minute" (all-inclusive) value of GHRs. He seamlessly leverages the Jan 2026 30% GHR price drop to win massive deals, navigates the paused SHR core platform charge ($0.002/min) to maintain customer trust, and strategically stacks Microsoft Azure Consumption Discounts (ACD) to close enterprise agreements. He relies heavily on the **Actions Telemetry Dashboard** to identify SHR churn risks and up-sell accounts to GHRs.
- **The Orchestration Fabric (AI & Security):** He drives full-platform multi-million dollar deals by positioning Actions as the foundational "orchestration fabric". He natively weaves in how Actions powers the entire GitHub ecosystem, from Copilot Coding Agents and GitHub Advanced Security (code/secret scanning) to developer VDI via Codespaces.
- **Ruthless Competitive Takeouts:** He expertly dismantles the competition using "Discovery 5.0" methodologies. He exposes Jenkins' massive hidden labor costs, points out GitLab CI's hidden premium seat pricing, and utilizes the **Actions Importer CLI utility** to forecast costs and prove GitHub's superior DevEx and TCO against CircleCI, BuildKite, and Azure Pipelines.

## How to Help Him With Work

- **Boardroom-Ready Demos:** When building demos, they must be flawless and deal-closing. The audience consists of Enterprise Architects, CISOs, and Platform VPs. Emphasize security (OIDC/VNET) and frictionless DevEx.
- **Ship Fast, Iterate:** When building tools, momentum is everything. Working code today beats perfect code next week.
- **Elevate the CI/CD Conversation:** Skip the YAML 101. Jump straight into the deep end: cross-repo OIDC trust, concurrency tuning, runner scale sets, and dynamic matrix strategies. 
- **Elite Workflow Standards:** Pin actions to exact SHAs, ruthlessly utilize OIDC for cloud auth (never long-lived secrets), implement concurrency groups to prevent queue bottlenecks, and maximize managed caching to slash build times.
- **TCO over Sticker Price:** When analyzing costs, sticker price is irrelevant. Focus on true TCO: expose the hidden costs of idle compute waste, Kubernetes management (ARC) headaches, networking egress, and dedicated maintenance headcount associated with SHRs.

## Enterprise-Grade Coding Standards

- **TypeScript strict mode.** No `any` unless unavoidable.
- **npm** — not pnpm, not yarn.
- **No enums** — use `as const` objects or union types.
- **Error handling** — try/catch for async, return early on errors, never swallow silently.
- **Naming:** `camelCase` variables/functions, `PascalCase` components/types, `SCREAMING_SNAKE` constants.
- **Comments explain WHY, not WHAT.** No obvious comments.
- **Don't over-abstract.** A 50-line function > 5 files of enterprise patterns.
