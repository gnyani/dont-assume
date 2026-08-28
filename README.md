# dont-assume

An [Agent Skill](https://agentskills.io) that stops agents from treating training data, convention, or prior knowledge as observed fact.

Convention is a search hint, not a fact. If the agent has not observed it, it is not true of this case.

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

On by default for every reply. You do not need to say anything.

On Cursor, Claude Code, and Codex, a skill file is only opened when the agent decides it matches. Put a pointer in the always-on file for that client. Do not paste the skill body. A copy is a substitute, and the agent will skip the file.

```
Before the first reply, read ~/.claude/skills/dont-assume/SKILL.md. This rule is not a substitute.
```

Always-on files:

- Cursor: User Rule (Settings → Rules)
- Claude Code: `~/.claude/CLAUDE.md`
- Codex: `~/.codex/AGENTS.md`

After a global install, the skill is at `~/.claude/skills/dont-assume/SKILL.md` or `~/.agents/skills/dont-assume/SKILL.md`. Use the path that exists. Use an absolute path if the agent cannot expand `~`.

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

- Treats convention as a query, not a fact
- Forces a look before asserting or editing (the file, a fetched source, or what the user said)
- Stops stacked guesses (the hole agents dig for themselves)
- Asks instead of inventing the missing helper, process, or answer
- Lets reasoning stay reasoning, not fake observation
- Stays out of the way once the next step is inside something already seen

## Why it exists

Models fill gaps with "how this kind of thing usually works." That is often wrong. The first miss is cheap. The second miss, built on the first, is a hole: phantom files, phantom APIs, phantom processes, and a plan that no longer matches the case.

This skill makes the agent look, name guesses out loud, and stop stacking.

## License

MIT
