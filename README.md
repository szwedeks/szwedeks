# Maciek Szwed

**Product leader, 15 years. I work out which AI bets are worth making, then build them myself.**

> [!NOTE]
> Looking for a product leadership role that is AI-related, or one I can make AI-related. Location open, willing to relocate.
> [m.r.szwed@gmail.com](mailto:m.r.szwed@gmail.com) · [LinkedIn](https://linkedin.com/in/maciek-szwed)

Most recently I ran the entire product function at a payments company in the Philippines: discovery, design, delivery, and the AI systems underneath it. Before that, eleven years at a Kraków consultancy, where I built the design organisation to thirty people and started the product function from nothing.

Most of what I build lives inside companies, so it gets written up rather than published. Here is one piece of it, in full.

## Letting an agent drive a bank

I needed an agent to operate a live banking application to produce customer-facing documentation. The interesting part is not what it did. It is the four separate places where it was forbidden to.

```mermaid
flowchart LR
  A(["Agent"]) --> G
  subgraph G["deny-by-default check, enforced at each call site"]
    direction TB
    DN{"navigate"}
    DC{"click"}
    DT{"type"}
    DE{"evaluate"}
  end
  G --> APP["Live banking app"]
  G -.-> B["Blocked, logged"]
  B -.->|human-vetted exception| APP
```

**Deny by default, enforced at every entry path rather than at one.** A single chokepoint is a single thing to forget, and the failure mode here is an agent moving somebody's money. Exceptions are vetted by a human, never by the model. Two complete builds, zero external state changes.

## Other systems I designed and shipped

<details>
<summary><b>An MCP server over live production data</b></summary>

Read-only access to our payments and analytics databases as permission-scoped tools, authorised per Google Workspace group, with every statement additionally wrapped in a READ ONLY transaction. Live schema introspection documents the known query traps so callers do not time the database out. Support answers "where is this payment" without an engineer; product gets contribution margin by method and by merchant.
</details>

<details>
<summary><b>Support tickets as a product signal</b></summary>

Every ticket classified and clustered into persistent issues, scored on recurrence <i>and</i> on how many distinct clients each one hits, so a single noisy merchant stays separable from a real product defect. It named our largest ticket category precisely enough to kill it with a product change.
</details>

<details>
<summary><b>Releases that write their own customer documentation</b></summary>

An LLM pipeline generating customer-facing release comms in production, with a human review gate. The gate caught a false statement on its way to a bank's help centre. The gate, not the generation, is the product decision worth talking about.
</details>

<details>
<summary><b>off-script</b> · a solo AI product, zero to live in twelve days</summary>

137 sources, n8n orchestration, local model enrichment, adapters, dedupe, scoring, a Telegram bot and an operator dashboard. I rebuilt the dashboard after admitting the first one was unreadable.
</details>

<details>
<summary><b>rubric-evals</b> · an eval harness for a scorer that had stopped saying yes</summary>

An overnight pipeline scored 21 startup ideas and returned essentially zero passes. The obvious conclusion was that every idea was bad. The question I asked instead was whether the rubric could say yes to anything at all. It could not, and the rubric became the thing under test.
</details>

## How I work

- **Measure the instrument first.** Before trusting a number, find out whether the thing producing it could ever produce a different one. Five times now, that question has been the whole finding.
- **Build it to find out.** A rough working version answers in days what a specification argues about for a quarter.
- **Say what went wrong.** Every write-up I do ends on something unresolved or something I got wrong. A portfolio of clean victories tells you nothing about how somebody thinks.

## Currently working with

`Claude Code` · `Python` · `n8n` · `Postgres` · `MCP` · `Ollama` · `PostHog` · `Grafana`

---

📍 Kraków · ✉️ [m.r.szwed@gmail.com](mailto:m.r.szwed@gmail.com) · 💼 [LinkedIn](https://linkedin.com/in/maciek-szwed)

<!-- Add once maciekszwed.com is live, and make it the primary link:
🌍 [maciekszwed.com](https://maciekszwed.com)
-->
