# Site Reliability Engineering — Training Deck

An interactive, self-contained SRE training deck built as a single HTML file. No build tools, no dependencies, no server required — just open it in a browser.

## Contents

28 slides covering the full SRE discipline:

| Section | Topics |
|---|---|
| **Foundations** | What is SRE, the SRE model vs traditional ops |
| **SRE Model** | Product outcomes, engineering mechanisms, decision levers |
| **Terminology** | SLI, SLO, SLA, error budgets defined |
| **Four Golden Signals** | Latency, traffic, errors, saturation |
| **Critical User Journeys** | Identifying and mapping CUJs |
| **SLI Specification** | Specification vs. implementation, SLI categories by service type |
| **SLI Design** | Choosing the right indicators |
| **SLO as Contract** | The SLO feedback loop |
| **SLO Design** | Setting targets with evidence |
| **SLO Math** | Nines reference table, rolling vs calendar window trade-offs |
| **Composite SLOs** | Why dependency chains multiply your ceiling down, worked example |
| **Error Budgets** | Budget policy, burn-down tracking |
| **Governance** | SLO review cadence and stakeholder alignment |
| **Alerting** | Burn-rate alerting — 14.4× / 6× / 1× tiers, two-window AND rule |
| **FMA & PRR** | Failure Mode Analysis and Production Readiness Review as pre-launch gates |
| **Progressive Delivery** | Canary/linear/blue-green rollout, automated rollback, feature flags, DORA metrics |
| **Postmortem Culture** | Blameless retrospectives, action tracking |
| **Toil** | Identifying and eliminating operational toil |
| **Cascading Failures** | Retry amplification, backoff+jitter, load shedding, graceful degradation |
| **Multi-Tenant Resilience** | Static stability, cell-based architecture, shuffle sharding |
| **EKS SaaS** | SRE patterns for Kubernetes-based SaaS |
| **Observability** | Pillars, tooling, correlation |
| **Anti-patterns** | Common SRE failure modes |
| **Incident Management** | On-call structure, severity levels |
| **On-Call Health** | Sustainable on-call practices |
| **SLO Review** | Running effective SLO review meetings |
| **Runbooks** | Writing actionable runbooks |
| **References** | Primary sources — Google SRE Book/Workbook, AWS and Azure Well-Architected Frameworks |

## Usage

Clone the repo and serve it with a local web server:

```bash
git clone https://github.com/jaredthivener/site-reliability-engineering.git
cd site-reliability-engineering
python3 -m http.server 8000
```

Then open `http://localhost:8000/sre-deck.html` in your browser.

Navigate with arrow keys or the sidebar. Toggle dark mode with the button in the top-right corner.

## Highlights

- **Burn-rate alerting** — the full Google SRE Workbook 3-tier model (14.4× / 6× / 1×) with correct window pairs, concrete arithmetic examples, a time-to-exhaustion reference table, and why the short window is a reset gate, not a detector
- **Composite SLOs** — why serial dependencies multiply your reliability ceiling down, worked through Azure's Well-Architected Framework example
- **SLO Math** — nines reference table, rolling (28-day) vs calendar window trade-offs
- **Error budget policy** — graduated response: feature freeze → incident response → postmortem required
- **Load-invariant alerting** — why raw error counts fail and burn rate (always relative to your SLO budget) doesn't
- **Cascading failures** — retry amplification across stack layers (3 retries × 3 layers = 64 attempts, not 27), backoff with jitter, retry budgets, load shedding
- **Multi-tenant resilience** — static stability, cell-based architecture, and the shuffle-sharding math (8 nodes / 2 per tenant → 56 combinations, ~1/56 blast radius)
- **Progressive delivery** — canary/linear/blue-green rollout with alarm-triggered automated rollback, feature flags, and how DORA's five metrics map onto it
- **FMA & PRR** — Failure Mode Analysis and Production Readiness Review as the concrete, checklist-driven answer to "how does SRE actually engage"

## Sources

Every corrected figure and every new slide is checked against a primary source, linked inline on the slide it supports:

- [Google SRE Book](https://sre.google/sre-book/table-of-contents/) and [SRE Workbook](https://sre.google/workbook/implementing-slos/)
- [AWS Well-Architected Framework — Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)
- [Azure Well-Architected Framework — Reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/checklist)

The full list is on the deck's own References slide.

## Stack

Vanilla HTML/CSS/JS — no frameworks, no bundler, no runtime dependencies. Google Fonts (IBM Plex Sans + IBM Plex Mono) loaded over CDN for typography.

## License

MIT
