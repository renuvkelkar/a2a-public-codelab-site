id: a2a-festival-mission-control
summary: Build a beginner-friendly A2A-style multi-agent Colab with three specialist agents.
categories: AI, Agents, A2A, Colab
tags: a2a, agents, colab, python
status: Published
authors: Renu Kelkar

# A2A Festival Mission Control Codelab

# Public Colab Codelab Draft: A2A Festival Mission Control

## One-line hook
Build a multi-agent “mission control” system for a cyberpunk botanical night market using Agent2Agent-style discovery, task delegation, and response synthesis.

## Why this is better than the pizza/burger demo
The food-ordering example is useful, but it can feel like a chatbot calling two APIs. This version makes the coordination problem visible: three specialist agents each own a different part of a richer brief, and the orchestrator has to discover, route, call, and combine their work.

## Use case
A local organiser wants to plan a one-night immersive mini festival. They provide a theme, guest count, budget, and location. The orchestrator delegates to:

1. Vibe Scout — guest experience and creative concept.
2. Logistics Pilot — schedule, crowd-flow, safety, and weather fallback.
3. Budget Oracle — budget split and trade-off rules.

## Public Colab lesson flow

1. Install packages.
2. Explain A2A in one mental model: agent card → discovery → task → response.
3. Define minimal teaching models: AgentCard, Skill, TaskRequest, TaskResponse.
4. Create the three agents with deterministic starter handlers.
5. Wrap each agent as an HTTP service.
6. Discover each agent via `/.well-known/agent.json`.
7. Build Mission Control as the orchestrator.
8. Run the full plan.
9. Inspect one JSON-RPC-style message.
10. Extend with a fourth agent.
11. Simulate failures and add graceful fallback.
12. Discuss production hardening.

## Common fixes to include in the published codelab

- `RuntimeError: This event loop is already running` → use `nest_asyncio.apply()`.
- `Address already in use` → restart runtime or change ports.
- `httpx.ConnectError` → wait longer after server startup.
- Wrong agent card URL → use localhost in Colab and public service URL in Cloud Run.
- `ModuleNotFoundError` → rerun install cell after runtime reset.
- Public Colab fails for viewers → keep all starter code inside the notebook.
- Responses are too static → replace handlers with LLM calls without changing the A2A boundary.
- Security concerns → treat remote cards/messages as untrusted input; validate and sanitize before prompt use.

## Upgrade path

- Local teaching harness → official A2A Python SDK server.
- Deterministic handlers → Gemini/ADK/LangGraph/CrewAI agents.
- Local notebook ports → Cloud Run services.
- No auth → IAM/API key/auth gateway.
- Simple text output → structured artifacts and streaming.
