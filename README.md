# Site Reliability Engineering — Training Deck

An interactive, self-contained SRE training deck built as a single HTML file. No build tools, no dependencies, no server required — just open it in a browser.

## Contents

22 slides covering the full SRE discipline:

| Section | Topics |
|---|---|
| **Foundations** | What is SRE, the SRE model vs traditional ops |
| **Terminology** | SLI, SLO, SLA, error budgets defined |
| **Four Golden Signals** | Latency, traffic, errors, saturation |
| **Critical User Journeys** | Identifying and mapping CUJs |
| **SLI Design** | Choosing the right indicators |
| **SLO as Contract** | The SLO feedback loop |
| **SLO Design** | Setting targets with evidence |
| **SLO Math** | Composite SLOs, nines table, rolling windows |
| **Error Budgets** | Budget policy, burn-down tracking |
| **Governance** | SLO review cadence and stakeholder alignment |
| **Alerting** | Burn-rate alerting — 14× fast burn, 1× slow burn, two-window AND rule |
| **Postmortem Culture** | Blameless retrospectives, action tracking |
| **Toil** | Identifying and eliminating operational toil |
| **EKS SaaS** | SRE patterns for Kubernetes-based SaaS |
| **Observability** | Pillars, tooling, correlation |
| **Anti-patterns** | Common SRE failure modes |
| **Incident Management** | On-call structure, severity levels |
| **On-Call Health** | Sustainable on-call practices |
| **SLO Review** | Running effective SLO review meetings |
| **Runbooks** | Writing actionable runbooks |

## Usage

```bash
# Clone and open — that's it
git clone https://github.com/jaredthivener/site-reliability-engineering.git
cd site-reliability-engineering
open sre-deck-enhanced.html     # macOS
# xdg-open sre-deck-enhanced.html  # Linux
```

Navigate with arrow keys or the sidebar. Toggle dark mode with the button in the top-right corner.

## Highlights

- **Burn-rate alerting** — explains the 14× and 1× multipliers with derivations, concrete arithmetic examples, a time-to-exhaustion reference table, and the two-window AND rule
- **SLO Math** — composite SLO derivation, nines reference table, rolling vs calendar window trade-offs
- **Error budget policy** — graduated response: feature freeze → incident response → postmortem required
- **Load-invariant alerting** — why raw error counts fail and burn rate (always relative to your SLO budget) doesn't

## Stack

Vanilla HTML/CSS/JS — no frameworks, no bundler, no runtime dependencies. Google Fonts (IBM Plex Sans + IBM Plex Mono) loaded over CDN for typography.

## License

MIT
