# margin

VS Code extension for understanding code you didn't write: a clickable map of the
codebase, predict-then-reveal explanations cited to exact lines, and notes that stay
true (or turn amber) as the code changes. Design: docs/designs/margin.md.

## Git workflow

- Every change goes through a feature branch (`feat/`, `fix/`, `docs/`, `spike/`), small commits, and a `--no-ff` merge back to main.
- Commit messages say what changed and why: `type(scope): what; why`.
- Push main and the branch after every merge so the history is visible on GitHub.
- No direct commits to main once code exists.

## Skill routing

When the user's request matches an available skill, invoke it via the Skill tool. When in doubt, invoke the skill.

Key routing rules:
- Product ideas/brainstorming → invoke /office-hours
- Strategy/scope → invoke /plan-ceo-review
- Architecture → invoke /plan-eng-review
- Design system/plan review → invoke /design-consultation or /plan-design-review
- Full review pipeline → invoke /autoplan
- Bugs/errors → invoke /investigate
- QA/testing site behavior → invoke /qa or /qa-only
- Code review/diff check → invoke /review
- Visual polish → invoke /design-review
- Ship/deploy/PR → invoke /ship or /land-and-deploy
- Save progress → invoke /context-save
- Resume context → invoke /context-restore
- Author a backlog-ready spec/issue → invoke /spec
