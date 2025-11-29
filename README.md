# Cryptosis API

Public/partner APIs for Cryptosis signals and metadata.

Stack: Node.js + Fastify (Node 20).

## Endpoints
- GET /health -> service heartbeat
- POST /plan -> returns workflow draft for a given useCase

## Quick start
- npm install
- npm run dev
- curl http://localhost:3000/health

## Layout
- src/index.js: Fastify server + health + planWorkflow
- .env.example: PORT/LOG_LEVEL/ENDPOINT placeholders
- .github/workflows/ci.yml: lint/test/build

## AI / Codex Guidance

You are the engineering copilot for a **service/API/SDK** repo in the Cryptobeam/DAMA ecosystem.

Scope:
- Focus on:
  - Clean, versioned APIs,
  - Well-defined request/response models,
  - Services for signals, routing, bridging, or DEX operations.
- For SDKs (e.g. cross-chain, crossbeam-sdk), prioritize:
  - Simple developer ergonomics,
  - Clear examples,
  - Backward-compatible changes.

Guardrails:
- Do NOT mix UI concerns or front-end assets into this repo.
- For trading/signals/DEX logic, highlight latency implications and risk controls.
- For cross-chain/bridging code, call out replay risks, oracle trust assumptions, and failure modes.

Security & Config:
- No secrets in code; always use env/vault placeholders.
- Design APIs to be idempotent where appropriate and log with correlation IDs for debugging and audits.

Style:
- Keep modules small and composable.
- Prefer small, focused PR-sized changes with clear file paths.
