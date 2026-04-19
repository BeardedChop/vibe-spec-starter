# AGENTS.md

this repo teaches AI tools to build from a written spec instead of a vague prompt.

## project overview

starter repo for spec-first AI-assisted development.

## tech stack

- **framework:** markdown-first template repo
- **language:** markdown
- **database:** none
- **auth:** none
- **deployment:** GitHub repo

## rules

### do
- read `SPEC.md` before proposing or generating implementation work
- preserve constraints, acceptance criteria, and failure conditions from the spec
- call out ambiguity instead of inventing requirements
- keep examples beginner-friendly and concrete
- prefer plain language over jargon
- restate the build target briefly before heavy implementation work

### don't
- don't skip the spec and jump straight to code
- don't add fake complexity to example apps
- don't overwrite constraints from the spec with your own preferences
- don't hardcode secrets or risky defaults in any example output
- don't treat open questions as permission to guess wildly

## code style

- short sections
- plain language
- examples should be easy for beginners to steal
- keep filenames literal and readable

## architecture notes

`SPEC.md` is the source of truth.
`CLAUDE.md` teaches Claude Code to consume the spec correctly.
`SPEC_EXAMPLE.md` shows what good looks like.
`TESTING_CHECKLIST.md` verifies the build matched the spec.
`context_rules.md` explains what should and should not go into the spec.
`docs/spec-teardown.md` explains why the structure works.

## how to use

1. fill out `SPEC.md`
2. make your AI read it first
3. build from that instead of repeated vague prompts

## documentation

- start with `README.md`
- use `context_rules.md` when deciding what belongs in the spec
- use `SECURITY.md` before shipping anything real

## security

- see `SECURITY.md`
- never place secrets in specs
- validate all user-facing requirements in real apps
