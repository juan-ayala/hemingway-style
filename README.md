# Hemingway Style

A two-pass editor for Claude. Pass 1 strips patterns common in AI-generated prose:

- Throat-clearing
- Forced binary contrasts
- Padded rule-of-three lists
- Dramatic em-dash pivots
- Hedging
- Fake agency for abstractions

Pass 2 applies Hemingway App-style readability rules: grade level, active voice, sentence length, and plain vocabulary.

This project has no affiliation with hemingwayapp.com, and they haven't endorsed it. The name credits their readability approach as inspiration for Pass 2. Pass 1 is original to this skill.

## Install

**Claude Code**
```
/plugin marketplace add juan-ayala/hemingway-style
/plugin install hemingway-style@hemingway-style
```

**Claude Desktop**

Download [`skills/hemingway-style/SKILL.md`](skills/hemingway-style/SKILL.md) from this repo, then Customize panel (left sidebar) → Skills → Add → Upload a skill → drag in the file. It's a single self-contained `.md` file — no zip needed.

**Any other Agent-Skills-spec tool** (Cursor, Codex, OpenCode, and more)
```
npx skills add juan-ayala/hemingway-style -a <agent>
# or: gh skill install juan-ayala/hemingway-style
```

Or copy `skills/hemingway-style/SKILL.md` directly. It's plain Markdown with no Claude-specific syntax.

## How this differs

Most existing Claude Code prose skills follow Strunk and White: concision, active voice, cut needless words. This skill adds a first pass that targets AI-generated-prose patterns before readability grading starts.

## Example

**Before**
> I'd be happy to help clarify this point. It's not just a minor issue — it's arguably one of the most important considerations here.

**After**
> This is one of the most important considerations here.

## License

MIT — see [LICENSE](LICENSE).
