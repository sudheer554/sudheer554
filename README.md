# Sudheer Mamillapalli

**AI Engineer · Forward Deployed Engineer** · Hyderabad, India

I build AI agents that do real business work, and the checks that keep them reliable: evals before a deploy, model failover, and tenant data isolation.

I came to AI from Linux administration (RHCE) and from running my own visa consultancy since 2019. So I ask two questions about every system: will it stay up, and does the business get value from it?

## What I'm building

**ZestForAI** is a multi-tenant AI platform for small businesses in India. Each business is a tenant with its own data, knowledge and AI workflows. Stack: FastAPI, Next.js, PostgreSQL 17, Redis, Celery, Docker. Self-hosted.

| Area | What I built |
|---|---|
| **Agents** | An orchestrator agent runs 6 departments: sales, marketing, content, finance, support and intelligence. Risky actions wait in an approval queue for a human. |
| **RAG** | Answers from each business's own documents. Hybrid retrieval: pgvector similarity plus PostgreSQL full-text search, merged with Reciprocal Rank Fusion, then a reranker with fallbacks if the reranking service is down. |
| **Evals** | A quality gate that runs before a deploy. It scores the production model on 11 golden sets (48 test items) and fails if any task scores below the floor. I do not deploy until it passes. |
| **Reliability** | An LLM gateway with failover across 4 providers, a circuit breaker and usage tracking. It kept serving through a real provider quota outage. |
| **API integrations** | An adapter layer that puts outside APIs behind one interface: 57 adapter files in 15 categories. In live use: WhatsApp Cloud API, LLM providers, Cloudflare R2. |
| **Data isolation** | PostgreSQL row-level security, forced on every tenant table, with a limited database role for the app. |
| **Indian languages** | Telugu voice replies on WhatsApp: speech-to-text → LLM → text-to-speech. |

Where it stands today: 7 tenants, all my own and family businesses. No paying customers yet. The code is private, so the case study shows how it works.

**Case study:** [ZestForAI: one AI platform for many small businesses](case-studies/zestforai.md)

## Public code

[claude-code-project-template](https://github.com/sudheer554/claude-code-project-template) is a starter for projects built with Claude Code. It has a small `CLAUDE.md`, skills, agents, tested safety hooks and an optional Python/FastAPI pack. It comes from how I set up my own projects: keep the always-loaded context small, and test the guard rails instead of trusting them.

## How I work

- **Evidence over claims.** If I have not measured a number, I do not state it.
- **Check quality before shipping.** A model or prompt change must pass the eval gate first.
- **No single point of failure.** Free models first, then a failover chain. Every outside provider sits behind an adapter, so it can be swapped.
- **Security from experience.** In April 2026 my server was compromised. I led the recovery and rebuilt the setup: network firewall, services bound to localhost, authentication in front of every service.
- **Write down why.** Each real decision gets a short record: what, why, and how to roll it back.

## Background

- **Founder & AI Engineer, ZestForAI** · Feb 2026 – present
- **Founder, Bhavishya Overseas** (visa and immigration consultancy) · 2019 – present. I own each client end to end: requirements, documents, follow-up and delivery.
- **Linux Administrator, Signin Soft** · 2015 – 2019. Servers, backups, monitoring and internal network security scanning.
- **Certifications:** RHCE and RHCSA (Red Hat, 2017)
- **Training in 2026 (Euron, ongoing):** Agentic AI Engineering · RAG Engineering · Backend System Design

## Skills

Python · FastAPI · PostgreSQL (row-level security) · Redis · Celery · Docker · CI/CD · Linux
LLM APIs (Anthropic, OpenAI-compatible, Gemini, Groq) · agents and orchestration · RAG (hybrid search, reranking, pgvector) · eval gates · model routing and failover · WhatsApp Cloud API · MCP (daily use)
Languages: English, Telugu

## Contact

[LinkedIn](https://www.linkedin.com/in/sudheer-mamillapalli-04538025) · open to AI Engineer and Forward Deployed Engineer roles
