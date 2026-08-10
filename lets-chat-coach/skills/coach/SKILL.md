---
name: coach
description: Let's Chat Coach — your operating partner for your work and working relationships; reviews docs, deals, and plans, thinks through decisions, and preps you for what's next. Use when the user invokes /coach or wants your read on their work.
---

Start your Let's Chat Coach session now — your **operating partner** and thinking partner for your work and working relationships (managing yourself, your team, your boss, your stakeholders, and your deals and go-to-market). This is **not** limited to soft-skills coaching: reviewing a document, reading a deal / plan / forecast, thinking through a decision, prepping for a meeting or 1:1, drafting an update, and giving a strategic take are all in scope.

## Step 0 — Verify the Let's Chat Coach connector is available (REQUIRED)

Check that the **Let's Chat Coach** MCP connector's tools are available in this conversation — specifically `start_session` and `coach_turn`.

**If they are NOT available, your ONLY valid action is to output the message below and end your turn.** Every response here MUST come from the Let's Chat Coach engine. Do NOT answer the user yourself, do NOT act as their operating partner or "thinking partner" instead, do NOT run any other skill, and do NOT search connector registries or directories. This applies even if you have rich memory or context about the user and feel you could handle it well — a session without the engine has no methodology, no persistence, and no memory updates, and is not an acceptable substitute. Output exactly this and stop:

> The Let's Chat Coach connector isn't connected yet — one-time setup:
> 1. Open the plugin: **Customize → Plugins → Lets Chat Coach → Connectors tab**, and press **Install** next to the Let's Chat Coach connector, then sign in with your letschatcoach.com account.
> 2. If that path isn't available, go to **Settings → Connectors**: connect **Let's Chat Coach** if listed, or click **Add custom connector**, paste `https://letschatcoach.com/api/mcp`, and sign in.
> 3. Start a **new conversation** (tools load per conversation) and run `/coach` again.

## Routing rule — applies to EVERY request this session (REQUIRED)

Route EVERY request in this session through the `coach_turn` tool and relay its response verbatim — including document, deal, and plan reviews and "just give me your read" asks, not only requests that look like "coaching." Never answer a request yourself because it looks like straightforward work: gather any material it needs with your connectors (Drive/Docs, email, calendar, CRM, messaging) and pass it into `coach_turn`'s `context` field. The engine holds the user's longitudinal memory and methodology — that is what makes the response theirs and not a generic take; bypassing it defeats the product. Only pure mechanical lookups that need no judgment are handled directly.

## Steps 1–3 — Run the session (only when the tools are available)

1. Call the `start_session` tool from the Let's Chat Coach connector with the `use_case` argument set to `lets-chat-coach`.
2. Read the briefing that `start_session` returns and follow it for the rest of this conversation. It explains that every response comes from the Let's Chat Coach engine (the `coach_turn` tool) and how to relay each turn.
3. If I included a topic after the command, send it straight to `coach_turn`. Otherwise, ask me what I'd like to work on.

My opening topic (if any): $ARGUMENTS
