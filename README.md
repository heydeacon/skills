# Deacon skills

Skills and an MCP server that let a coding agent add [Deacon](https://heydeacon.com) to your site or app, then read what your customers tell it.

Deacon is an AI support chat for your site. It answers your customers from your own docs and pages, says when it doesn't know, and shows you what people keep asking. There's a free plan.

| Skill | What it does |
| ----- | ------------ |
| `deacon-install` | Puts the Deacon widget on every page, tells it who is signed in, and checks a real page has loaded it. |
| `deacon-goals` | Sends goals from your app, like sign ups and upgrades, so Deacon's dashboard counts them. |
| `deacon-connect` | Connects your coding agent to Deacon, so it can read what customers reported and help fix it. |

Each skill carries its whole guide. The guides are also published at https://heydeacon.com/agent/install.md, https://heydeacon.com/agent/goals.md and https://heydeacon.com/agent/connect.md.

## Examples

- "Install Deacon on this site. My key is pk_..."
- "Tell Deacon who is signed in and what plan they're on."
- "Add Deacon goals for sign ups, paywall hits and upgrades."
- "What broke this week?"
- "Deacon couldn't answer this. Read the code and suggest an answer."

## The MCP server

The plugin also adds Deacon's MCP server, at `https://heydeacon.com/mcp`. When a customer tells Deacon's chat that something's broken, your coding agent can read it, find the cause in your code and show you the fix. It's on every plan, including the free one.

**What it reads.** Your conversations, the What needs you list, topics, the JavaScript errors on your site, and what Deacon knows: your pages, texts, files and help document. It sees a customer's email only when it opens their conversation, never in a list.

**What it changes.** Two things, and neither reaches your customers. It can mark a topic done, which you can undo with Show again. And it can suggest a better version of one of Deacon's answers, which waits in Conversations until someone on your team saves it.

**What it can't do.** Reply to anyone, change what Deacon knows or add webhooks. Deacon never touches your code. Your agent does the fixing, on your machine, when you say yes.

**Signing in.** There's no key to copy. Your browser opens on Deacon, you choose the team and press Allow. Only an owner of the team can allow it, and every owner gets an email when an agent connects or disconnects. Connected agents are listed under Coding agents on the Integrations page, where you can disconnect them. Devin Desktop (Windsurf), scripts and CI use a Coding agent key from Integrations instead.

**Keep your agent's approvals on.** Anyone can type anything into a chat, including instructions aimed at your agent. Deacon marks everything a stranger wrote as data and tells your agent not to follow it, but no marking is foolproof. Read a change that came from a customer's report as you'd read a pull request from a stranger.

Every tool, and what each returns, is under MCP server in the API docs at https://heydeacon.com/docs/api#mcp-server.

## What it sends

To check its work, `deacon-install` asks `https://heydeacon.com/api/widget/seen` whether a page has loaded the widget, and `deacon-goals` asks `https://heydeacon.com/api/goals/recent` which goals have arrived. Both send only your site's public widget key.

The code the skills add to your site loads Deacon's widget from heydeacon.com. If your app has signed-in users, `deacon-install` also passes each one's id, email and name to Deacon, so you can see who you're talking to.

The plugin's only other address is Deacon's MCP server. The plugin carries no key, so your agent can't use the server until an owner allows it. After that, your agent sends Deacon what it asks for, such as a search, and any answer it suggests.

Deacon's privacy policy is at https://heydeacon.com/privacy.

## Install

Claude Code:

```
/plugin marketplace add heydeacon/skills
/plugin install deacon@heydeacon
```

Then run `/mcp`, pick the deacon server and choose Authenticate.

If you've already connected Deacon in Claude Code, or as a claude.ai connector, there's nothing to do. Claude Code keeps that connection and leaves out the plugin's copy.

Other agents that read skills:

```
npx skills add heydeacon/skills
```

Then ask your agent to connect to Deacon. The `deacon-connect` skill adds the server for Claude Code, Codex, Cursor and VS Code.

Or skip the plugin. Point your agent at https://heydeacon.com/agent/install.md to add Deacon to your site, or https://heydeacon.com/agent/connect.md to connect it to Deacon.

You'll need a Deacon account. Sign up at https://heydeacon.com/register. The install skill also needs your key from the Install page.

## Help

Open an issue here, or email hello@heydeacon.com. Send security problems to the same address.

## License

MIT
