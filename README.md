# Deacon skills

Skills that let a coding agent add [Deacon](https://heydeacon.com) to your site or app.

Deacon is an AI support agent. It answers your customers from your own docs and pages, says when it doesn't know, and shows you what people keep asking. There's a free plan.

| Skill | What it does |
| ----- | ------------ |
| `deacon-install` | Puts the Deacon widget on every page, tells it who is signed in, and checks a real page has loaded it. |
| `deacon-goals` | Sends goals from your app, like sign ups and upgrades, so Deacon's dashboard counts them. |

Each skill carries its whole guide. The same guides are published at https://heydeacon.com/agent/install.md and https://heydeacon.com/agent/goals.md.

## Examples

- "Install Deacon on this site. My key is pk_..."
- "Tell Deacon who is signed in and what plan they're on."
- "Add Deacon goals for sign ups, paywall hits and upgrades."

## What it sends

To check its work, `deacon-install` asks heydeacon.com whether a page has loaded the widget, and `deacon-goals` asks which goals have arrived. Both send only your site's public widget key.

The code the skills add to your site loads Deacon's widget from heydeacon.com. If your app has signed-in users, `deacon-install` also passes each one's id, email and name to Deacon, so you can see who you're talking to. Deacon's privacy policy is at https://heydeacon.com/privacy.

## Install

Claude Code:

```
/plugin marketplace add heydeacon/skills
/plugin install deacon@heydeacon
```

Other agents that read skills:

```
npx skills add heydeacon/skills
```

Or skip the install and point your agent at https://heydeacon.com/agent/install.md.

You'll need a Deacon account and your key from the Install page. Sign up at https://heydeacon.com/register.

## Help

Open an issue here, or email hello@heydeacon.com. Send security problems to the same address.

## License

MIT
