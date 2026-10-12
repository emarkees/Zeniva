# Zeniva
AI layer that investigates failed bank transactions and prepares
human-approved resolutions in minutes. It never moves money.

Zecathon 6.0, Track 2: AI-Powered Transaction Investigation and Resolution.
Demo data is synthetic. The demo uses a mock bank API.

## What it does
- Links complaints from every channel to transaction evidence
- Finds failed transactions before customers complain (journal sweep)
- Tracks regulatory reversal deadlines per case
- Prepares one batch reversal request for human approval
- Declines false claims with evidence; never refunds twice

## Architecture
Web (React) -> API (FastAPI) -> adapter layer -> mock bank API (demo) or bank API (pilot)
Postgres with pgvector, Redis, background workers, LLM gateway.

## Repository layout
web/  api/  mock_bank/  ai/  seed/  infra/  docs/

## Quick start
Prerequisites, then the commands from the setup steps (Section 87 of the spec).
make up | make seed | make test | make demo-reset

## Safety principles
No payment-initiation code. Read-only bank access. PII masked before AI calls.
Every AI claim cites record IDs. No real customer data in this repo.

## Team
Frontend, Backend, AI/ML and data, Product/UI-UX (names and roles)

## Links
Pitch deck, specification, demo script (in docs/)
