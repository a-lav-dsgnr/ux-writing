# UX Writing Skills

AI writes interface copy that looks more or less fine but needs the same fixes every time. Buttons that say "OK" or "Submit". Errors that blame the user and never say how to fix the problem. Three "options" that are the same sentence reworded three times.

This skill gives the agent a process instead of a vague goal. It asks only about the things that change the copy, picks three different approaches, and explains in one line why each one works.

## Install

```bash
npx skills@latest add a-lav-dsgnr/ux-writing
```

Or just copy the skill folder into `~/.claude/skills/`.

## Skills

- **[ux-writing](./skills/ux-writing/SKILL.md)** writes or rewrites in-product copy: buttons, errors, empty states, onboarding, confirmations, tooltips. You get three variants, each with a different strategy and a short note on why.

## What it looks like

Rewriting a login error: "Error 403: Invalid credentials. Please try again."

```
1. Title: Check your email or password
   Button: Try again
   → Fix-first: leads with what to do and drops the code and "please"

2. Title: That email and password don't match
   Description: Check for typos, or reset your password.
   Button: Reset password
   → Cause + fix: says what happened without blaming, then offers a way out

3. Title: Couldn't sign you in
   Description: Your account is safe. Check your email and password, then try again.
   Button: Try again
   → Reassure + fix: calms a user worried about a breach before giving the fix
```

If something feels off, open an issue. The skill is still being tested on real projects, so it will keep changing.
