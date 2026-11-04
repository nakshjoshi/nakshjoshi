## Nakshatra Joshi

Backend and AI infrastructure engineer. Final-year B.Tech. in Computer Science & Design Engineering at RGIPT.

I work on the layer underneath LLM products — retrieval pipelines, agent tooling, job queues, auth, and the deployment plumbing that keeps them running in production.

**Available from January 2027** for a 6-month internship or full-time role.

[Portfolio](https://nakshjoshi.in) · [LinkedIn](https://www.linkedin.com/in/nakshjoshi/) · connect.nakshjoshi@gmail.com

---

### Experience

**Software Engineer Intern** — CargoFL (Innoctive Technologies) · May – Aug 2026 · Pune

Re-platformed a chat-based freight-procurement agent off a Fastify agent marketplace — where per-agent tools were isolated on Cloudflare Workers + D1 — first into a standalone Workers backend, then into an independent Fastify + React service on PostgreSQL/Drizzle. Implemented 10 tools covering the end-to-end RFQ lifecycle across 7 carriers, with background workers handling per-client configurable sweep intervals for stale-RFQ reminders and failed-job retries, and write-only BYOK credentials encrypted at rest. Validated with 5 MCP-driven Playwright E2E flows and 50 test RFQs; passed client UAT on 30 RFQs.

Also built the backend of an AI proof-of-delivery extraction platform: file-type routing into a Redis queue backed by a Postgres job table, pulling documents from S3 on demand for an OCR + vision-LLM pass. Extended line-item-to-total reconciliation to every file-type path — **~82% of production PODs auto-reconcile**, the rest route to manual review. **7,000+ PODs processed in production.** Implemented RBAC across 5 roles for single-tenant deployments serving 3 clients with client-hosted databases for data residency.

**AI Developer Intern** — Prodigal AI · Jun – Aug 2025 · Remote

Built FastAPI backends for RAG-based content-generation pipelines, orchestrated as Airflow DAGs with human-in-the-loop steps that pause for reviewer approval and persist conversation history in a separate store, so runs resume rather than restart. Used the MLflow Model Registry (DagsHub) to load versioned models at runtime, enabling model swaps without redeploys.

---

### Projects

#### [Swiftly](https://github.com/nakshjoshi/swiftly) — resume automation platform · [live](https://swiftly.nakshjoshi.in)
`Next.js` `TypeScript` `Bun` `Express` `Prisma` `PostgreSQL` `Gemini` `Docker`

A Next.js dashboard, Bun/Express REST API, and WXT MV3 browser extension for job-application autofill. Auth is custom, with no third-party provider: JWT with refresh-token rotation, Google OAuth2, and WebAuthn passkeys.

An LLM parsing pipeline turns PDF/DOCX/LaTeX resumes into schema-validated JSON in normalized PostgreSQL via Prisma. A two-stage autofill maps extracted DOM field metadata to profile values with event-safe injection for React, Vue and Svelte forms. LaTeX compilation is isolated in a resource-limited Docker service (1 GB / 1 CPU, 60 s timeout, per-job temp dirs), built in GitHub Actions CI/CD behind type-check and lint gates, pushing SHA-tagged images to Docker Hub and deploying the pinned SHA over SSH to AWS EC2 as health-checked, non-root containers. **100+ resumes processed** from testing to production.

#### [Bilingual AI Chatbot](https://github.com/nakshjoshi/MySchemeMultiLinguaBot) — CRAG over government schemes
`Python` `Streamlit` `ChromaDB` `SentenceTransformers` `Gemini 2.0 Flash`

A Hindi↔English CRAG retrieval system over **3,300+ Indian government schemes**, reaching **85%+ answer accuracy** on an LLM-as-judge evaluation across a generated question set. Metadata-enriched hybrid chunking (30K+ chunks) with Top-2 + sibling retrieval cuts token overhead, and intent detection routes queries between eligibility, benefits, and how-to-apply paths.

#### [Voice AI Agent](https://github.com/nakshjoshi/stt-llm-tts) — real-time speech pipeline
`React` `Node.js` `Express` `Groq` `OpenAI` `Whisper` `Orpheus TTS`

A mic → STT → LLM → TTS agent (Whisper-large-v3-turbo, GPT-OSS-20B, Orpheus) behind an Express API, provider-swappable between Groq and OpenAI via a single environment variable. Browser-speech fallback, rate-limit-aware sentence trimming, and typed 429/502/503 error handling.

#### GoBrics — hackathon platform
`React` `Node.js` `Express` `Turborepo` `PostgreSQL` `Prisma` `Redis` `AWS` `Yandex Cloud`

Team build serving **10K+ users across India and Russia** at **1K+ concurrent**. Built upload APIs with S3 integration for PDF submissions and a Redis-queued email service respecting Resend rate limits. Co-designed Route 53 geolocation routing to localise Russian data on Yandex Cloud, sharing one S3-SDK codebase with AWS.

---

### Currently building

**Sentinel** — semantic conflict detection for parallel AI coding agents. Git merges line by line, so when one agent renames `createOrder` and another adds a call to it in a different file, the merge is clean and the code is broken. Sentinel watches every agent's edits as they happen and resolves which changes actually interact, across three tiers of increasing cost and certainty.

**Meter** — an AI gateway with quota and cost control: per-team token budgets enforced across distributed instances, exact cost per request, caching, multi-provider failover, and usage billing on a double-entry ledger.

---

### Technical skills

**Languages** — TypeScript/JavaScript, Python, Java, SQL, Bash

**Backend & web** — Node.js, Fastify, Express, Hono, FastAPI, Bun, React, Next.js, REST APIs, OAuth2/WebAuthn

**AI/LLM** — RAG, LLM tool calling, MCP, ChromaDB, LangChain, OCR + vision LLMs, MLflow, Airflow, Whisper/TTS

**Data & infra** — PostgreSQL, Redis, Prisma/Drizzle, Docker, GitHub Actions, AWS (EC2/S3), Cloudflare Workers/D1, Linux

---

### Education

**Rajiv Gandhi Institute of Petroleum Technology** — B.Tech. in Computer Science & Design Engineering · Aug 2023 – May 2027 · CPI 7.43

Training and Placement Student Coordinator (2024 – present), coordinating placements and internships at RGIPT.
KodeKurrent Hackathon 2025 — finalist from 250+ teams; converted to a paid internship at Prodigal AI.
