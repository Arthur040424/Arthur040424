# Arthur Mulunda

Software Engineer based in Nairobi, Kenya. Third-year Computer Science student at The Kiambu Institute of Science and Technology, building production-grade systems and developing a strong bias toward backend engineering and system architecture.

I care about understanding how systems work before writing code — schema design, data flow, failure handling — not just making things run.

---

## What I'm Building

### FlowX

![Node.js](https://img.shields.io/badge/Backend-Node.js_%2B_TypeScript-339933?style=flat-square)
![Next.js](https://img.shields.io/badge/Frontend-Next.js_14-black?style=flat-square)
![BullMQ](https://img.shields.io/badge/Queue-BullMQ_%2B_Redis-DC382D?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL_16-336791?style=flat-square)
![Claude](https://img.shields.io/badge/AI-Anthropic_Claude_API-D97757?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Development-orange?style=flat-square)

> Real-time data pipeline orchestrator for small engineering teams — from drag-and-drop pipeline design to live execution monitoring and AI-powered failure diagnosis.

**The problem:** Small data teams run on unsupervised cron jobs. Scripts fail silently, retries don't happen, dependencies go undocumented, and the first sign of trouble is often a broken dashboard days later. Tools like Airflow, Prefect, and Dagster solve this for teams with dedicated DevOps — not for a 3-person startup data team.

**The solution:** FlowX is a visual pipeline builder where steps are nodes on a drag-and-drop canvas, execution runs as background jobs with automatic retries, and every step's status streams live to the UI as it happens. On failure, an AI assistant reads the failure context and explains what broke and how to fix it, in plain English.

**System components**

| Component | Role | What it does |
|---|---|---|
| Pipeline Canvas | Visual editor | Xyflow-based drag-and-drop DAG builder — define steps and dependencies without writing code |
| API Server | Core backend | Express + TypeScript REST API — pipeline CRUD, run triggers, auth |
| Job Queue & Workers | Execution engine | BullMQ + Redis — topological execution order, retries with exponential backoff, dead-letter handling |
| Real-Time Layer | Live monitoring | WebSocket server + Redis pub/sub — step status pushed to the canvas within milliseconds |
| AI Debug Assistant | Failure diagnosis | Claude API reads step config, error, and run history — returns a plain-English diagnosis and fix |

**Tech stack:** Node.js · Express · TypeScript (strict) · BullMQ · Redis · WebSockets (`ws`) · PostgreSQL 16 · Next.js 14 (App Router) · Tailwind CSS · Xyflow · Auth.js (GitHub OAuth) + JWT · Anthropic Claude API · Docker Compose · GitHub Actions → Railway + Vercel

```
Pipeline Canvas (Xyflow) → API Server (Express) → BullMQ (Redis-backed)
                                  ↓                        ↓
                          PostgreSQL              Worker Pool (executes steps)
                                  ↑                        ↓
                       WebSocket Server  ←——  Redis Pub/Sub
                                  ↓
                          Live Run Monitor
                                  ↓ (on failure)
                          AI Debug Assistant (Claude API)
```

**Status:** 🚧 In active development — Phase 1 of 9. Infrastructure (Docker, PostgreSQL, Redis, monorepo) is live; TypeScript foundations underway. Built in public, one phase at a time — [follow the build →](https://github.com/Arthur040424/flowx)

---

### AttachIQ

![Python](https://img.shields.io/badge/Python-FastAPI-009688?style=flat-square)
![Next.js](https://img.shields.io/badge/Frontend-Next.js_15-black?style=flat-square)
![Google ADK](https://img.shields.io/badge/AI-Google_ADK_%2B_Gemini-4285F4?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Development-orange?style=flat-square)

> AI-agent-powered platform for managing TVET industrial attachment assessment in Kenya — from placement to competency sign-off.

**The problem:** Kenya's 700+ TVET colleges require every student to complete a 3-month industrial attachment under the CBET curriculum. Assessment runs on paper logbooks that supervisors don't understand and students fill in retrospectively — coordinators only see issues once the student is back. Students graduate with paper qualifications that don't reflect real competency.

**The solution:** AttachIQ replaces the paper workflow with a multi-tenant web platform and four AI agents that guide every stakeholder in real time, covering the full lifecycle: placement → evidence collection → competency assessment → coordinator monitoring → compliance reporting.

**AI agents**

| Agent | Role | What it does |
|---|---|---|
| StudentIQ | Student coach | Tracks competency gaps, guides evidence submission, drafts messages to supervisors |
| SupervisorIQ | Supervisor guide | Walks non-educator supervisors through CBET assessment conversationally — no rubrics, no jargon |
| CoordIQ | Coordinator intelligence | Surfaces at-risk students, flags coverage gaps, generates batch reports on demand |
| AttachIQ Core | Orchestrator | Routes incoming requests and coordinates cross-agent workflows |

**Tech stack:** Next.js 15 (App Router) · TypeScript · shadcn/ui · Python FastAPI · Pydantic v2 · SQLAlchemy 2.0 (async) · Google Agent Development Kit (ADK) · Gemini 2.0 Flash · PostgreSQL 16 (16-table, multi-tenant schema) · Cloudinary · JWT (access + refresh rotation) · Vercel + Google Cloud Run + Railway · GitHub Actions → Docker → Cloud Run

```
Client (Next.js) → FastAPI → ADK Orchestrator → [StudentIQ | SupervisorIQ | CoordIQ]
                                  ↓ tool calls
                            PostgreSQL · Cloudinary · Gemini API
```

**Market:** 700+ TVET institutions across Kenya's 47 counties, hundreds of thousands of students on attachment annually, no direct competitor in this space. Pricing model: KSH 3,000–10,000/month per institution, with an expansion path into Uganda, Tanzania, and Rwanda under the same CBET framework.

**Status:** 🚧 In active development — full production build in progress.

---

### Copy Cat Job Card System ✓ Completed

A field operations management platform built and deployed for Copy Cat Group. Supervisors manage the full job lifecycle while technicians update job status from the field through a role-gated interface.

- Five security layers: authentication, route-level authorisation, role-based data access, input validation, and rate limiting
- M-Pesa Daraja API (STK Push) integration — payment collection triggered directly from the job card on completion, with state tracked in the database
- Auto-generated PDF reports per job card for record-keeping and customer handover
- Monitoring dashboard (Python · FastAPI) tracking API health, database performance, M-Pesa transaction states, and user activity — with email alerts and exportable reports

**Stack:** Node.js · Express · PostgreSQL · React · Tailwind CSS · Python · FastAPI

---

## Tech Stack

**Languages:** TypeScript · JavaScript · Python · SQL
**Frontend:** React · Next.js 15 · Tailwind CSS · shadcn/ui · Xyflow
**Backend:** Node.js · Express · FastAPI · Pydantic v2 · SQLAlchemy 2.0
**AI/Agents:** Anthropic Claude API · Google Agent Development Kit (ADK) · Gemini 2.0 Flash
**Databases:** PostgreSQL · Redis · Prisma ORM
**Infrastructure:** Docker · BullMQ · WebSockets · Cloudinary · GitHub Actions · Railway · Vercel · Google Cloud Run
**Integrations:** M-Pesa Daraja API · Anthropic Claude API · Google ADK
**Tools:** Git · Postman · Linux (Ubuntu)

---

## What I'm Working Toward

Backend engineering and system architecture. I want to understand systems well enough to design them — how data moves, where failures happen, how services communicate, and how to build something that holds up under real load. That's the level I'm working toward.

---

## Reach Me

[arthurmulunda941@gmail.com](mailto:arthurmulunda941@gmail.com)
