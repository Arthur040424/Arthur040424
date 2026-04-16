# Arthur Mulunda

Full stack developer based in Nairobi, Kenya. Third-year Computer Science student at The Kiambu National Polytechnic, building production-grade systems and developing a strong bias toward backend engineering and system architecture.

I care about understanding how systems work before writing code — schema design, data flow, failure handling — not just making things run.

---

## What I'm Building

### FlowX
A production-grade visual data pipeline orchestration platform. Pipelines are built on a drag-and-drop canvas and executed asynchronously using a job queue architecture. Built for engineering teams who need enterprise reliability without heavy DevOps overhead.

- Job queue layer powered by BullMQ and Redis with priority queues, retry logic, and dead-letter queue handling
- Real-time execution monitoring over WebSockets — live step-by-step pipeline status broadcast to the canvas as jobs run
- AI-powered debug assistant using the Anthropic Claude API — reads failed step logs and returns plain-English explanations with fix suggestions
- Multi-tenant credential vault with encrypted storage for API keys and secrets, scoped per workspace
- Containerised with Docker for consistent local development and deployment

**Stack:** Node.js · TypeScript · PostgreSQL · BullMQ · Redis · WebSockets · Docker · Next.js

---

### Attachment Assessment System
A cloud platform to digitise industrial attachment (internship) assessments for Kenyan TVET colleges and polytechnics. Currently in pre-build phase — system design is complete, a 16-table schema aligned with Kenya's CBET curriculum model is built, and the multi-tenant architecture is defined before application code begins.

**Stack:** Next.js 15 · Express · TypeScript · Prisma · PostgreSQL · Cloudinary

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
**Frontend:** React · Next.js 15 · Tailwind CSS  
**Backend:** Node.js · Express · FastAPI  
**Databases:** PostgreSQL · Redis · Prisma ORM  
**Infrastructure:** Docker · BullMQ · WebSockets · Cloudinary  
**Integrations:** M-Pesa Daraja API · Anthropic Claude API  
**Tools:** Git · Postman · Linux (Ubuntu)

---

## What I'm Working Toward

Backend engineering and system architecture. I want to understand systems well enough to design them — how data moves, where failures happen, how services communicate, and how to build something that holds up under real load. That's the level I'm working toward.

---

## Reach Me

arthurmulunda461@gmail.com
