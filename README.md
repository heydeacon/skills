# Deacon skills

Skills that let a coding agent add [Deacon](https://heydeacon.com) to your site or app.

Deacon is an AI support agent. It answers your customers from your own docs and pages, says when it doesn't know, and shows you what people keep asking. There's a free plan.

| Skill | What it does |
| ----- | ------------ |
| `deacon-install` | Puts the Deacon widget on every page, tells it who is signed in, and checks a real page has loaded it. |
| `deacon-goals` | Sends goals from your app, like sign ups and upgrades, so Deacon's dashboard counts them. |

Each skill fetches its guide from heydeacon.com when it runs, so it's always current.

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

## License

MIT
