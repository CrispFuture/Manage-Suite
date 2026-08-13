# Manage Suite by Crisp Future

An **operating partner**, inside Claude, for your deals, your team, your boss, and your stakeholders — that remembers you across conversations. Installing this plugin adds:

- the **"Manage My…" shortcuts** — one operator lens per relationship you manage (yourself, your team, your boss, your stakeholders),
- a **`/coach`** skill for executive coaching, and
- the **Manage Suite connector** (our operating-partner engine).

### Shortcuts

| Shortcut | Focus |
| --- | --- |
| `/manageme` | Manage yourself — your own deals, week, priorities, and managing up. |
| `/manageteam` | Manage your team — delegation, feedback, performance, team dynamics. |
| `/manageboss` | Manage your boss — managing upward, alignment, trust. |
| `/managestakeholders` | Manage your stakeholders — influence, alignment without authority. |
| `/coach` | Executive coaching — career, leadership, tough conversations, and judgment calls. |

Every shortcut runs through the same Manage Suite engine and connector. The `/manageme` shortcut and `/coach` are live today. Some of the other **Manage My…** shortcuts may route to products that aren't live on your account yet — when that happens the shortcut tells you it isn't active, shows what you do have access to, and stops, rather than improvising. As those products go live, the shortcuts light up automatically — no plugin update or reinstall needed.

Manage Suite runs on the Crisp Future engine and is relayed into your conversation, so it applies your own methodology, history, and memory across sessions.

> **Updating:** to pick up a new version, open **Plugins → Personal → ⋯ → Check for updates**. Turn on **Sync automatically** to keep it current.

---

## Install (Claude Pro / Max)

**Option A — from this repo (recommended):**

1. In Claude, open **Customize** (left sidebar) → **Plugins**.
2. Add a marketplace pointing at this repository: `https://github.com/CrispFuture/Manage-Suite`.
3. Install the **manage-suite** plugin.

**Option B — upload the package:**

1. Download the plugin package (the `manage-suite` folder, or a zip of it).
2. In Claude, open **Customize** → **Plugins** → upload a custom plugin, and select it.

### Step 2 — install the Manage Suite connector (required, one time)

Installing the plugin does **not** automatically connect or sign you in — Claude requires you to approve any connector yourself. Before your first session:

1. Open the plugin's page: **Customize → Plugins → Manage Suite by Crisp Future**, switch to the **Connectors** tab, and press **Install** next to the Manage Suite connector. Sign in with your [crispfuture.com](https://crispfuture.com) account when prompted.
2. Alternatively (or if you don't see the Connectors tab): go to **Settings → Connectors**, connect **Manage Suite** if listed, or click **Add custom connector** and paste `https://crispfuture.com/api/mcp`, then sign in.
3. Start a **new conversation** — Claude loads a connector's tools per conversation, so an existing chat won't see them.

Don't have a Crisp Future account yet? Sign up at [crispfuture.com](https://crispfuture.com) first.

## Use

In a chat, type the lens you want:

```
/manageme
```

…or start with a topic:

```
/manageme help me prep for the pipeline review with my boss
```

Then just talk. Every reply comes from the Manage Suite engine. Use `/manageme`, `/manageteam`, `/manageboss`, or `/managestakeholders` for the relationship you're working on, or `/coach` for executive coaching.

---

## What's in here

```
.claude-plugin/marketplace.json     # marketplace catalog
manage-suite/
├── .claude-plugin/plugin.json      # plugin manifest
├── .mcp.json                       # connects the Manage Suite engine (crispfuture.com/api/mcp)
└── skills/
    ├── manageme/SKILL.md           # the /manageme shortcut
    ├── manageteam/SKILL.md         # the /manageteam shortcut
    ├── manageboss/SKILL.md         # the /manageboss shortcut
    ├── managestakeholders/SKILL.md # the /managestakeholders shortcut
    └── coach/SKILL.md              # the /coach skill
```

## Troubleshooting

- **A shortcut runs the wrong thing or says the skill doesn't exist:** make sure the connector is connected (Step 2 above), then start a new conversation. If you have other skills with similar names, use the namespaced form, e.g. `/manage-suite:manageme`.
- **No sign-in prompt ever appeared:** connect via **Settings → Connectors** (Step 2) — the sign-in happens there, not during plugin install.
- **"Access denied" from Manage Suite:** your Crisp Future trial or subscription may be inactive — check your plan at [crispfuture.com](https://crispfuture.com).

Learn more: [crispfuture.com](https://crispfuture.com)
