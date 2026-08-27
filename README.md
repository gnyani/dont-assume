# dont-assume

An [Agent Skill](https://agentskills.io) that stops coding agents from treating training-data conventions as facts about *this* repo.

Convention is a search hint, not a location. If the agent has not observed it here, it is not true here.

Works with Cursor, Claude Code, and any client that supports Agent Skills.

## Install

```bash
npx skills add gnyani/dont-assume        # this project
npx skills add gnyani/dont-assume -g     # all projects
```

## Use

It should load on its own when the agent is implementing, debugging, or exploring a codebase.

You can also say:

```
dont-assume
don't assume
look first
don't guess
```

Stop:

```
stop dont-assume
```

Also works: `assume away`.

## What it does

- Treats convention as a query, not a file path
- Forces a look at the real file, symbol, route, or schema before editing
- Stops stacked guesses (the hole agents dig for themselves)
- Asks instead of inventing a missing helper, util, or folder
- Stays out of the way once the next edit is inside something already read

## Why it exists

Models fill gaps with "how this kind of project usually works." That is often wrong. The first miss is cheap. The second miss, built on the first, is a hole: phantom files, phantom APIs, extra packages, and a plan that no longer matches the repo.

This skill makes the agent look, name guesses out loud, and stop stacking.

## License

MIT
