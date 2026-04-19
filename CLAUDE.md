# CLAUDE.md

import AGENTS.md

## claude-specific rules

before generating code or architecture from this repo:

1. read `SPEC.md`
2. extract the required stack, features, constraints, acceptance criteria, and failure conditions
3. restate the plan briefly before coding if the task is implementation-heavy
4. when something is missing, ask for the missing requirement instead of guessing
5. if the spec is weak, suggest tightening the spec before writing a bunch of code

## working rule

the spec wins.
if a prompt conflicts with `SPEC.md`, stop and call out the conflict.

## output rule

when proposing implementation from a spec:
- reference the relevant section of the spec
- preserve the stated constraints
- verify the final result against acceptance criteria
- call out any failure condition that still looks risky after implementation
