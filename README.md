## Muhammad Zuhaib Zahid

I build backend systems with an AI component, where the interesting part isn't calling the model,
it's everything around it: retries, cost control, failure handling, and knowing whether the thing
actually works.

**Currently working in** Python · FastAPI · Postgres · Docker

**Previously** TypeScript · Electron · React

Open to backend, AI engineering and AI automation roles.

---

### Selected work

**[rag-ablations](https://github.com/muhzuhaib/rag-ablations)**: retrieval benchmark that states its baseline

Most RAG projects claim they improved retrieval without saying what they improved it over. This one
measures every design choice (chunking, sparse vs dense vs hybrid, reranking) against classical BM25
on public corpora with real relevance judgments. The BM25 baseline is validated against the published
BEIR figures, and CI re-runs the benchmark on every push, so the numbers in the README cannot drift
away from the code. Runs on a laptop CPU with no API keys.

`Python · FastAPI · sentence-transformers · Docker`

**[ci-triage](https://github.com/muhzuhaib/ci-triage)**: reads a failing CI build and answers it, for at most a fixed amount of money

A webhook service that fetches the failed jobs' logs, asks an LLM what broke, and posts one comment on
the pull request. The interesting part is not the LLM call. The spend ceiling is a guarantee rather
than a hope, enforced inside the database's own lock so concurrent workers cannot race past it, and the
comment is posted exactly once even though webhooks get redelivered and workers get killed mid-run. A
failure-injection suite kills the worker at each seam, and it found a real defect that 235 passing
tests had walked past.

`Python · FastAPI · Postgres · Docker`

**[Orbit](https://github.com/muhzuhaib/orbit)**: a multi-model desktop AI client

A cross-platform Electron app that talks to Anthropic, Google, Groq, OpenAI-compatible and local Ollama
models through one interface. Ships with auto-update, a runtime rate-limit circuit breaker that demotes
models after repeated quota errors, keyless web search, and encrypted local backup. ~25 releases.

`TypeScript · Electron · React`

**[Seekr](https://github.com/muhzuhaib/seekr)**: a desktop job-search client

Fetches and normalises listings, handles pagination and rate limits, backfills company data in the
background, and caches results locally. Built around a reader-window pool with per-lane concurrency to
keep fetches fast without tripping upstream limits.

`TypeScript · Electron`

---

### In progress

Small, finished tools extracted from real use, published properly rather than left as gists. Links
here as they land.

---

📫 Reachable through GitHub.
