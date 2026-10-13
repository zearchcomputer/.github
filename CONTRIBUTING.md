# Contributing to Zearch

Thanks for helping. Zearch is a research engine that checks every paragraph against its sources before you see it. Contributions that make answers easier to check are the most welcome.

## Ways to help

- **Quality reports.** An answer cited the wrong page, or said something its source doesn't say. Use the *Quality report* issue form. These are the most useful reports we get.
- **Bugs and features.** Use the issue forms. Search open issues first.
- **Code.** Start with an issue labelled `good-first-issue`, or open an issue to discuss a larger change before you build it.

## Ground rules

- **The stack stays small.** Backend: Python standard-library HTTP handlers. Frontend: vanilla JS, no framework. No new heavy dependencies. A stack change needs an ADR in `docs/adr/` first.
- **New features ship off.** Put them behind a `ZEARCH_*` flag that defaults to off.
- **No secrets.** Never commit keys, tokens or `.env` values, and never paste them into issues, logs or test fixtures. `.env.example` lists variable names only.
- **The brand is locked.** See [BRAND.md](https://github.com/zearchcomputer/zearch/blob/main/BRAND.md) and [docs/BRAND_MESSAGING.md](https://github.com/zearchcomputer/zearch/blob/main/docs/BRAND_MESSAGING.md). Copy is clear, curious and restrained; no hype words.
- **Schema changes are additive.** Rolling back code must never require dropping data.

## Development

```sh
python -m pip install -r requirements.txt
python research_store.py   # create the local SQLite schema
python server.py           # http://localhost:8765
```

Set the variables named in `.env.example` in your shell. The app does not load `.env` files by itself.

## Before you open a pull request

Run all three; CI runs them too and every PR must pass:

```sh
python -m unittest discover -s tests
node tests/renderer.test.js
node tests/core.test.js
```

Tests use isolated SQLite and mocked providers, so they make no paid calls. Do not add tests that call Tavily, TypeSafe, OpenAI or Stripe.

## Pull requests

- Work on a branch; never push to `main`. A maintainer reviews and merges.
- Keep PRs small and focused. Moves and refactors go in separate PRs from behavior changes.
- Fill in the PR template, including the deployment notes: flags, Vercel changes and the exact Railway values if a start command or Dockerfile path changes.
- Wait for the Vercel preview deploy to succeed and check your change there.

## Labels

| Prefix | Values |
|---|---|
| `type/` | `bug`, `feature`, `quality`, `docs`, `chore`, `refactor` |
| `area/` | `retrieval`, `jev`, `ui`, `billing`, `api`, `infra`, `brand` |
| `priority/` | `p0` (now), `p1` (next), `p2` (later) |
| | `good-first-issue` |

## License

By contributing you agree that your contribution is licensed under the MIT License of the repository you contribute to.
