# Claude Code Best Practices

19 best practice files that keep AI-generated code production-ready. Grounded in standards like RFC 9457, WCAG 2.2, OWASP Top 10, and DAMA-DMBOK, not opinions.

These are part of my Claude Code setup, refined over 2,000+ hours of iteration. They work by giving the model deep knowledge about how production software should work, so it makes better decisions in situations you never anticipated.

## What's in here

| File | What it prevents |
|------|-----------------|
| [Layered Architecture](best-practices/layered-architecture.md) | Business logic in API handlers, untestable code |
| [Error Handling](best-practices/error-handling.md) | Swallowed errors, generic "something went wrong" messages |
| [Testing Strategy](best-practices/testing-strategy.md) | Tests that mock everything and prove nothing |
| [API Design](best-practices/api-design.md) | Inconsistent errors, missing pagination, exposed stack traces |
| [Data Integrity](best-practices/data-integrity.md) | Race conditions, partial failures, broken migrations |
| [Structured Logging](best-practices/structured-logging.md) | `console.log("it worked")` in production |
| [Authorization](best-practices/authorization.md) | Missing permission checks, IDOR vulnerabilities |
| [Defense-in-Depth Validation](best-practices/defense-in-depth-validation.md) | Injection attacks, path traversal, single-layer validation |
| [Container Security](best-practices/container-security.md) | Root containers, baked secrets, bloated images |
| [Privacy by Design](best-practices/privacy-by-design.md) | GDPR violations, missing consent, no right to erasure |
| [Resilience Patterns](best-practices/resilience-patterns.md) | Cascading failures, no timeouts, unbounded retries |
| [Zero-Downtime Deployment](best-practices/zero-downtime-deployment.md) | Downtime during deploys, broken migrations |
| [Observability](best-practices/observability.md) | Blind spots in production, no correlation between logs |
| [Accessibility](best-practices/accessibility.md) | Unusable interfaces for keyboard/screen reader users |
| [SEO and Geo-Targeting](best-practices/seo-and-geo.md) | Orphan pages, missing structured data, broken hreflang |
| [Robots and Scraping](best-practices/robots-and-scraping.md) | AI crawlers training on your content, unprotected APIs |
| [Background Job Patterns](best-practices/background-job-patterns.md) | Lost jobs, no idempotency, no graceful shutdown |
| [LLM Integration Patterns](best-practices/llm-integration-patterns.md) | Expensive calls for deterministic work, unparsed output |
| [Performance Optimization](best-practices/performance-optimization.md) | Premature optimization, unmeasured tuning, wrong data structures |

## How to use

Drop the files into a directory your Claude Code setup can reference. The model picks them up without special configuration, they just need to be part of the context.

You don't need to load all 19 files every time. Load what's relevant:
- **Planning a feature?** Load the architecture, error handling, and testing files.
- **Reviewing a PR?** Load the files relevant to what changed.
- **Building an API?** Load API design, error handling, authorization.

Each file follows the same structure: a principle, a "why" section explaining what goes wrong without it, core rules with code examples, and common mistakes.

## The system behind these files

These best practices are one layer of a three-layer system:

1. **Requirements** define what must be true (e.g., REQ-API-001: error responses must follow RFC 9457)
2. **Specifications** define how to implement each requirement, with traceability
3. **Best practices** (this repo) provide the deep knowledge, the why, the trade-offs, the patterns

The requirements and specifications are not included here yet. The best practices work on their own, but they're more powerful as part of the full chain.

## Blog series

These files are discussed in detail in a three-part blog series:

- [Part 1: Architecture, Error Handling, Testing, API Design, Data Integrity, Structured Logging](https://albertsikkema.com/ai/development/best-practices/2026/03/31/evidence-based-best-practices-ai-guardrails.html)
- Part 2: Security, Privacy, and Production Hardening (coming soon)
- Part 3: Domain-Specific Guardrails (coming soon)

## Standards referenced

- [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) - Problem Details for HTTP APIs
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) - Web Content Accessibility Guidelines
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) - Web Application Security Risks
- [DAMA-DMBOK](https://www.dama.org/cpages/body-of-knowledge) - Data Management Body of Knowledge
- [ePrivacy Directive](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A02009L0136-20201221) - Cookie/consent requirements
- [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32016R0679) - General Data Protection Regulation

## Support

If these files save you time, consider buying me a coffee:

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-support-yellow?style=flat&logo=buy-me-a-coffee)](https://buymeacoffee.com/albertsikkema)

## License

MIT License. Free to use. Adapt to your stack, your standards, your needs.
