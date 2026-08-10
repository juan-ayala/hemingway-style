---
name: hemingway-style
description: Two-pass editor for human-read prose. Pass 1 strips AI-slop patterns (throat-clearing, forced contrasts, rule-of-three padding, dramatic em-dashes, hedging, fake agency). Pass 2 applies Hemingway-App-style readability rules (grade level, active voice, sentence length, jargon). Use when writing or editing prose meant for a human reader — README files, docs, blog posts, cover letters, emails — or when the user asks to edit, proofread, clean up, or tighten writing. A calling project's own instructions (e.g. CLAUDE.md) can narrow or override this default.
---
# Hemingway Style

Two-pass editor, outgoing human-read text. Pass 1 strip AI slop pattern. Pass 2 use [hemingwayapp.com](https://hemingwayapp.com/) grade rule: short, direct, active prose, fast easy read. Run both pass, in order, every text skill touch.

## Scope

Default trigger: see description above. Calling proj instruction (e.g. `CLAUDE.md`) can narrow, broaden, override default — keep skill generic reusable, no edit here new use case come.

## Pass 1: Stop Slop (Anti-AI)

Strip pattern below before touch readability. Sign of AI prose, not sign of good writing:

- **Throat-clearing.** Cut preamble before point — "I'd be happy to help with that," "Great question," "Let's dive in." Start w/ point.
- **Binary contrasts.** Cut "Not X, but Y", "It's not just X — it's Y", "is X, not Y" (e.g. "unreliable output, not a deterministic parser"). State real claim direct, skip straw-man knock-down.
- **Forced rules-of-three.** Don't pad list to three item just for rhetoric. Use as many item as content need.
- **Dramatic em-dash setups.** Cut "here's the surprising part —" or "and that changes everything" pivot. State fact, let land on own.
- **Softening hedges.** Cut "arguably," "perhaps," "in many ways," "to some extent," similar hedge word. If true, say true.
- **Fake agency for abstractions.** Don't give human agency to concept, tool, process — "this approach empowers teams to..." or "the framework wants you to...". Name real actor: who do what.

## Pass 2: Hemingway Readability

Run after Pass 1:

**Grade**: Target 6th-8th grade level. Bold, clear, direct prose.

**Adverbs**: Cut `-ly` word + qualifier ("just," "very," "really," "basically"). Use one strong verb instead of weak verb + adverb ("sprinted" over "ran quickly").

**Voice**: Strict active voice. No passive (e.g., "I achieved," not "Was achieved by me").

**Vocabulary**: Auto-swap complex word for plain:
- utilize -> use
- facilitate -> help
- implement -> start / run
- terminate -> end
- subsequent -> next

**Length**: Split sentence over 20-25 word. Shorter usually better, don't force choppy for own sake — grade level real target, not word count.

**Structure**: Word count alone under-predict difficulty. Sentence under 20 word still hard read if stack clause complexity: 3+ item list, parenthetical or em-dash aside, trailing participial clause ("...styled by X," "...following Y"), or 2nd independent clause joined "and"/"so." Split when two stack one sentence, even under word cap.

**Layout**: Paragraph max 1-3 sentence. Heavy bullet for scan (under 6 sec scan).

**Final sweep**: Before deliver, re-scan once for: passive voice ("is/are/was/were/been" + past participle), 4 banned qualifier (just, very, really, basically), any surviving Pass 1 binary-contrast phrase. Pattern most likely survive first read — check explicit, don't trust already caught. Sweep applies old text too: reapply skill to old content mean run both pass full, not just check what change since last edit.

## Examples

**Before (Pass 1 — AI slop):**
> I'd be happy to help clarify this point. It's not just a minor issue — it's arguably one of the most important considerations here. The system basically empowers teams to move faster, and this approach really helps streamline the whole process.

**After:**
> This is one of the most important considerations here. The system lets teams move faster and simplifies the process.

**Before (Pass 2 — readability):**
> The report was reviewed by the team, and after some discussion, it was decided that the new process, which had been proposed by the engineering group and which involved several complex steps, would be implemented gradually over the next few quarters.

**After:**
> The team reviewed the report and decided to adopt the new process. Engineering proposed it. It involves several complex steps, so it rolls out gradually over the next few quarters.

## Output

Deliver only final edited text by default. No meta-commentary, no change log, no "Pass 1 removed X, Pass 2 fixed Y" summary — unless user ask explicit for diff or explain of change.