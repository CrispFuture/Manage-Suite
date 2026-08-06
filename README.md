# Let's Chat Coach — Claude plugin

Professional coaching from the **Let's Chat Coach** engine, delivered inside Claude. Installing this plugin adds:

- a **`/coach`** skill to start a coaching session,
- the **"Manage My…" shortcuts** — one per relationship you manage, and
- the **Let's Chat Coach connector** (our coaching engine).

### Shortcuts

| Shortcut | Focus |
| --- | --- |
| `/coach` | General coaching — leadership, career, goals, tough conversations. |
| `/manageme` | Manage yourself — self-leadership, focus, resilience, growth. |
| `/manageteam` | Manage your team — delegation, feedback, performance, team dynamics. |
| `/manageboss` | Manage your boss — managing upward, alignment, trust. |
| `/managestakeholders` | Manage your stakeholders — influence, alignment without authority. |
| `/managework` | Manage your work — prioritization, planning, boundaries. |

Every shortcut runs through the same Let's Chat Coach engine and connector. The `/manageme` shortcut and `/coach` are live today. Some of the other **Manage My…** shortcuts may route to products that aren't live on your account yet — when that happens the shortcut tells you it isn't active, shows what you do have access to, and stops, rather than improvising coaching. As those products go live, the shortcuts light up automatically — no plugin update or reinstall needed.

Coaching runs on the Let's Chat Coach engine and is relayed into your conversation, so it applies your own methodology, history, and memory across sessions.

---

## Install (Claude Pro / Max)

**Option A — from this repo (recommended):**

1. In Claude, open **Customize** (left sidebar) → **Plugins**.
2. Add a marketplace pointing at this repository: `https://github.com/letschatcoach/Lets-Chat-Coach`.
3. Install the **lets-chat-coach** plugin.

**Option B — upload the package:**

1. Download the plugin package (the `lets-chat-coach` folder, or a zip of it).
2. In Claude, open **Customize** → **Plugins** → upload a custom plugin, and select it.

### Step 2 — install the Let's Chat Coach connector (required, one time)

Installing the plugin does **not** automatically connect or sign you in — Claude requires you to approve any connector yourself. Before your first session:

1. Open the plugin's page: **Customize → Plugins → Lets Chat Coach**, switch to the **Connectors** tab, and press **Install** next to the Let's Chat Coach connector. Sign in with your [letschatcoach.com](https://letschatcoach.com) account when prompted.
2. Alternatively (or if you don't see the Connectors tab): go to **Settings → Connectors**, connect **Let's Chat Coach** if listed, or click **Add custom connector** and paste `https://letschatcoach.com/api/mcp`, then sign in.
3. Start a **new conversation** — Claude loads a connector's tools per conversation, so an existing chat won't see them.

Don't have a Let's Chat Coach account yet? Sign up at [letschatcoach.com](https://letschatcoach.com) first.

## Use

In a chat, type:

```
/coach
```

…or start with a topic:

```
/coach help me prep for a tough 1:1 with my report
```

Then just talk. Every reply comes from the Let's Chat Coach engine.

---

## What's in here

```
.claude-plugin/marketplace.json     # marketplace catalog
lets-chat-coach/
├── .claude-plugin/plugin.json      # plugin manifest
├── .mcp.json                       # connects the Let's Chat Coach engine (letschatcoach.com/api/mcp)
└── skills/
    ├── coach/SKILL.md              # the /coach skill
    ├── manageme/SKILL.md           # the /manageme shortcut
    ├── manageteam/SKILL.md         # the /manageteam shortcut
    ├── manageboss/SKILL.md         # the /manageboss shortcut
    ├── managestakeholders/SKILL.md # the /managestakeholders shortcut
    └── managework/SKILL.md         # the /managework shortcut
```

## Troubleshooting

- **`/coach` runs the wrong thing or says the skill doesn't exist:** make sure the connector is connected (Step 2 above), then start a new conversation. If you have other skills with similar names, use the namespaced form: `/lets-chat-coach:coach`.
- **No sign-in prompt ever appeared:** connect via **Settings → Connectors** (Step 2) — the sign-in happens there, not during plugin install.
- **"Access denied" from the coach:** your Let's Chat Coach trial or subscription may be inactive — check your plan at [letschatcoach.com](https://letschatcoach.com).

Learn more: [letschatcoach.com](https://letschatcoach.com)
