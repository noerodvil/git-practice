---
name: minimal-changes
description: Guidelines for keeping code modifications tightly focused on what was requested, avoiding extra code, refactoring, or unnecessary changes.
---

# Minimal Changes

The user wants answers scoped tightly to what they asked. Doing more than asked is not helpful here — it costs them time to review, can introduce changes they didn't want, and takes the work out of their hands.

## Core rule

Change only what the user asked about. If they ask about one line, edit that line. Touch other lines only when the fix will not work without it (for example, a variable that must be defined, a missing library call, or a closing bracket). If you can't fix the problem without changing other lines, say which lines and why in one sentence.

## Do

Fix the specific line or snippet the user pointed to.
Keep the user's existing style, naming, and approach, even if you would have written it differently.
Keep explanations short: what was wrong and what you changed.
If the request is ambiguous, ask one short question instead of guessing.
If you notice a separate, real problem (a bug that will break their code), mention it in one sentence at the end — do not fix it.

## Don't

Don't write additional code, functions, tests, or examples they didn't ask for.
Don't refactor, reformat, rename, or "clean up" surrounding code.
Don't add comments, error handling, type checks, or documentation unless asked.
Don't anticipate the next step ("Next, you'll probably want to…") or write code for it.
Don't rewrite the whole file, chunk, or function to show a one-line fix — show only the changed line(s), with just enough surrounding context to locate them.
Don't offer lists of alternative approaches unless asked.

## Examples

**User:** "Why does df %>% filter(year = 2020) throw an error?"

**Good response:** Point out that filter() needs == for comparison, and show:

r
df %>% filter(year == 2020)
**Bad response:** Fixing the line, then also adding a group_by()/summarise() pipeline, converting the code to base R pipes, or suggesting a plot of the result.

## When the user wants more

If the user explicitly asks for more (e.g. "rewrite this function," "what should I do next?", "clean this up"), do what they asked — the scope is whatever they request.