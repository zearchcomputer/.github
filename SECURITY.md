# Security policy

## Reporting a vulnerability

Please report security issues **privately** through GitHub:
[Report a vulnerability](https://github.com/zearchcomputer/zearch/security/advisories/new).

Do not open a public issue, pull request or post for a security problem.

Include what you can:

- what an attacker could do, and to whom
- the affected route, file or flow
- steps to reproduce, or a minimal proof of concept
- whether you have seen it exploited

We aim to acknowledge a report within 3 business days and to share a plan within 10. We'll tell you when it's fixed and credit you in the advisory if you want.

## In scope

- The hosted app at zearch-computer.vercel.app and its `/api/*` and `/v1/*` routes
- This repository's code, including the Railway workers
- Workspace isolation: one browser or account reading another's answers, notes, documents or captures
- Authentication, sessions, OAuth, API keys, credits and billing
- Server-side request forgery through Scrape, Crawl, Reverse engineer or uploads
- Cross-site scripting through answers, source cards or rendered model output

## Out of scope

- Answer quality on its own (wrong citations, unsupported claims). Use the *Quality report* issue form.
- Denial of service through volume, and rate-limit tuning
- Findings in third-party providers (Tavily, TypeSafe, OpenAI, Stripe, Vercel, Railway); report those to the provider
- Missing headers or best practices with no demonstrated impact

## Testing rules

- Only test against accounts and data you own.
- Do not run automated scanners against the hosted app, and do not spend provider credits at volume.
- Reverse engineer mode analyzes software statically; only submit software you are authorized to inspect.

## Supported versions

Only the current `main` branch and the hosted app are supported.
