---
name: ux-writing
description: Write or rewrite in-product UX copy (English) using UX writing best practices. Use this skill whenever the user wants to create or improve interface text — buttons, CTAs, error messages, empty states, onboarding, tooltips, confirmation dialogs, notifications, form labels, microcopy — or asks to "apply UX writing best practices," "rewrite this string," "make this copy better," or invokes /ux-writing. Trigger even when the user just pastes a piece of interface text and asks to improve it, without naming "UX writing" explicitly.
---

# UX Writing

Write English in-product copy. Walk the same five steps every time: lock the format, fill only the context gaps that change the words, pick three strategies from the table, write inside the hard limits, check before sending.

If the user shares a brand voice, style guide, or character limit, it overrides every default below.

## Step 1 — Lock the format

Formats: `text` · `button` · `title + description` · `title + description + button`

```
Did the user name the format, or paste an existing string to rewrite?
├── Named → use it.
├── Pasted a string → keep that string's format (a pasted button stays a button).
└── Neither → ask. Put the question in the same message as any Step 2 questions.
```

Every variant has exactly the requested parts — never add a button the user didn't ask for, never drop one they did. Why: a variant with the wrong parts can't be compared side by side; the designer has to rebuild it first.

## Step 2 — Ask only what changes the copy

```
Do I know where the text appears (button, toast, modal, empty state, tooltip, email)?
└── No → ask. Placement sets the length limit and the tone.

Is it an error, a failure, or a destructive action?
└── Yes, and I don't know the cause or how the user recovers → ask.
    The fix is the one part of an error I must never invent.

Do I know what the user just did or is trying to do?
└── No, and the copy depends on it → ask.

Character limit, brand voice, existing product terms unknown?
└── Don't ask. Use Step 4 defaults and state the assumption.
```

Maximum 3 questions, in one message. If nothing needs asking, write immediately and put assumptions in one line at the top: `Assuming: mobile button, ~20 characters, casual product voice.` Why: every question costs the user a round trip — only ask when the answer would flip what you write.

## Step 3 — Pick three different strategies

Always exactly 3 variants. Each uses a different strategy from the row that matches the moment. Rewording the same idea ("Save changes" / "Save your changes" / "Save edits") is one variant, not three.

| Moment | Variant 1 | Variant 2 | Variant 3 |
|---|---|---|---|
| Error / failure | Fix-first: lead with what to do | Cause + fix: what happened, then what to do | Reassure + fix: what's safe, then what to do |
| Destructive confirmation | Consequence-first ("This can't be undone") | Minimal, names the exact object | Offers the safer alternative (archive, disable) |
| Empty state | Next action | Value: what will appear here and why it matters | Minimal neutral |
| Onboarding / feature intro | Benefit-first | Action-first | Concrete example or number |
| Success / milestone | Minimal confirmation | Celebratory | What's next |
| Labels, tooltips, settings | Shortest possible | Most explicit | Outcome-framed (what happens when on) |

Never playful in errors, destructive confirmations, payments, security, or data loss. Why: the user is anxious or about to lose something; a joke reads as not taking that seriously.

## Step 4 — Write inside the hard limits

Defaults (user constraints override):

- **Button:** 1–3 words. Verb + object ("Save changes", "Delete file"). Never "OK", "Submit", "Yes", "No". Why: screen readers and scanning eyes read the button alone — it must make sense without the title.
- **Destructive button repeats the title's verb:** "Delete project?" → "Delete". Why: if the title says "Remove" and the button says "Delete", the user doubts which button does what.
- **Title:** ≤ 6 words, ≤ 40 characters, sentence case, no period.
- **Description:** ≤ 2 sentences, ≤ 120 characters.
- **Errors:** what happened + what to do. Never blame: "You entered an invalid date" → "Enter a date after today." Error codes only after the human message, never instead of it.
- **Cut on sight:** "please", "simply", "just", "successfully", "in order to", "you are able to", "please note that". Why: they cost width and add nothing; "simply" and "just" tell a stuck user the task was easy, which stings.
- **Voice:** address the user as "you". Mention the system ("we") only when it failed: "We couldn't save your changes." Why: owning the failure takes blame off the user.
- **Terms:** reuse the exact nouns and verbs from the user's input and surrounding UI. If they said "workspace", never write "project". Why: a new word makes users think it's a different thing.
- **Decline options stay neutral:** "Not now", "No thanks". Never guilt ("No, I don't want to save money"), never fake urgency. Why: manipulative copy wins one click and loses trust.
- **Rewrites** keep the original's meaning and size class — a button stays button-length.
- American English spelling.

## Step 5 — Check who controls the outcome before writing a button

```
Can the current user make the outcome happen with this button?
├── Yes → primary action button.
└── No (waits on a teammate, approval, sync, someone else)
    → No primary CTA. Use no button, or one the user can actually act on:
      "Learn how it works", "Invite a teammate".
      If the format asked for a button, say so in one line and give the informational one.
```

Why: a button that can't make the thing happen promises control the user doesn't have.

## Output

Copy goes straight into the chat. No file unless asked. No intro paragraph, no closing summary.

```
Assuming: … (only if you assumed something)

1. Title: …
   Description: …
   Button: …
   → Strategy — why, in one sentence naming the principle

2. …
```

Single-part formats drop the labels: `1. "Save changes"` then the `→` line.

## Before sending, check every variant

- [ ] Exactly the requested parts
- [ ] Three different strategies from the Step 3 row, not three rewordings
- [ ] Inside the Step 4 length limits
- [ ] Buttons are verb + object; no OK / Submit / Yes / No
- [ ] No word from the "cut on sight" list
- [ ] Every error has a fix and no blame
- [ ] Same terms as the user's input
