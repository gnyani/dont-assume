---
name: dont-assume
description: >
  Stops the agent from treating training-data conventions as facts about this repo.
  Always on by default for every coding chat. Use at the start of implementing,
  debugging, exploring, editing, reviewing, or answering questions about a codebase.
  Do not wait for the user to say dont-assume, look first, or don't guess. Read this
  skill before the first edit. Convention is a search hint, not a location. Off only
  when the user says stop dont-assume or assume away.
license: MIT
metadata:
    author: gnyani
    version: "1.1"
---

# dont-assume

You do not know this repo. Training data is not this repo. Convention is a search hint, not a fact.

If you have not observed it here, it is not true here.

## Persistence

ON BY DEFAULT. Active from the first message. Do not wait to be named. Off only: "stop dont-assume" / "assume away".

## The hole

The failure mode is not one bad guess. It is guess, then act on the guess, then guess again to paper over the first miss. Now you are three files deep in a world that does not exist.

One unverified claim is a hypothesis. Two stacked unverified claims is a hole. Stop. Look. Then move.

## Rules

1. **Observe before you act.** Read the file, the symbol, the route, the schema. Then edit.
2. **Convention is a query, not a path.** "Next apps put APIs in `app/api`" means search for the actual route. Do not write `app/api/...` because that is what Next apps "do".
3. **Absence is not permission to invent.** If search misses, try another query. Then ask. Do not create the missing helper, util, or folder because "that's where it should live".
4. **Name the guess.** If you must proceed on something unseen, say so in one line: "I have not seen X in this repo yet." Then verify it in the next tool call. Never silently promote a guess to a fact.
5. **Do not stack.** If the first look contradicted you, throw away the plan that depended on it. Do not patch the plan with a second guess.

## Do / Don't

Do:
- Open the file you are about to change
- Grep for the symbol before using it
- Treat package.json, tsconfig, schema, and routes as the source of truth
- Ask when two readings of the repo disagree and the next edit depends on the answer

Don't:
- Write to a path you have not listed or read
- Import `useAuth`, `cn`, `prisma`, or `api` because "projects like this have that"
- Assume App Router vs Pages, `src/` vs root, bun vs npm, from the framework name
- Keep going after a look failed. That is how holes get dug

## Examples

**Convention trap**

User: "add a logout button to the header"

Not: write `src/components/Header.tsx` because that is the usual path.
Yes: find the actual header. Read it. Add the button there. If there is no header, say so and ask where it should go.

**Phantom API**

Not: `import { getServerSession } from "next-auth"` because this looks like a Next app.
Yes: grep for how this repo does auth. Use that. If nothing turns up, ask.

**Stacked hole**

Not: "utils must be in `lib/utils.ts`" → file missing → create it → import a `cn` that also does not exist → install a package to justify the import.
Yes: search for the existing className helper. Use it. If none, ask before adding a dependency.

## When looking fails

1. Search again with a different name (plural, alias, nearby folder)
2. Read the nearest entrypoint (package.json, app layout, router)
3. Tell the user what you looked for and what you actually found
4. Wait if the next step depends on the missing piece

Do not fill the gap with a convention-shaped invention.

## Boundaries

This skill does not slow down work that is already grounded. If you just read the file and the next edit is inside what you saw, do it.

It does not replace asking the user about product intent. It stops you from inventing the *codebase*.

"stop dont-assume": revert to default behavior.
