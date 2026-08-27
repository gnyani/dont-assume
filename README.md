# dont-assume

An [Agent Skill](https://agentskills.io) that stops coding agents from treating training-data conventions as facts about *this* repo.

Convention is a search hint, not a location. If the agent has not observed it here, it is not true here.

Works with Cursor, Claude Code, and any client that supports Agent Skills.

## Install

[![skills.sh](https://skills.sh/b/gnyani/dont-assume)](https://skills.sh/gnyani/dont-assume)

[![Install in Cursor](https://img.shields.io/badge/Install_in-Cursor-000000?style=for-the-badge)](https://cursor.com/link/prompt?text=Install+the+dont-assume+skill+globally+for+Cursor.+Run+this+command%2C+then+start+a+new+chat%3A%0A%0Anpx+skills+add+gnyani%2Fdont-assume+-g+-a+cursor+-y)
[![Install in Claude Code](https://img.shields.io/badge/Install_in-Claude_Code-D97706?style=for-the-badge)](#claude-code)
[![Install in Codex](https://img.shields.io/badge/Install_in-Codex-10A37F?style=for-the-badge)](#codex)

Any agent:

```bash
npx skills add gnyani/dont-assume -g
```

This project only: drop the `-g`.

### Cursor

The button opens Cursor with the install command. Or run:

```bash
npx skills add gnyani/dont-assume -g -a cursor -y
```

### Claude Code

```bash
npx skills add gnyani/dont-assume -g -a claude-code -y
```

### Codex

```bash
npx skills add gnyani/dont-assume -g -a codex -y
```

## Use

On by default. The agent should load it at the start of any coding chat. You do not need to say anything.

Optional reminders:

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
