# context_rules.md

what belongs in a spec, and what does not.

## put this in the spec
- the actual job of the product
- who it is for
- stack choices that matter
- the main features
- data model basics
- routes / screens
- auth and permissions
- non-negotiable constraints
- clear acceptance criteria
- clear failure conditions when relevant

## do not put this in the spec
- giant motivational paragraphs
- vague goals like "make it modern"
- random brainstorm ideas you are not committing to
- secrets, keys, tokens, or passwords
- implementation details you do not actually care about
- five different future versions of the product

## good examples

### bad
- make it clean and scalable
- maybe add payments later
- maybe there should be teams too

### better
- use sqlite for v1
- no teams in v1
- only signed-in users can create and delete records
- every mutation must be server-validated

## what usually needs defaults
- routing choice
- delete behavior
- time zone/date handling
- validation rules
- acceptable deployment shortcuts

## what usually blocks implementation
- auth model is missing entirely
- user roles are unclear
- ownership/privacy rules are unclear
- the deployment/storage setup is contradictory
- acceptance criteria depend on decisions that were never made

## rule of thumb

if the AI needs the information to make a correct product decision, it belongs in the spec.
if it is just noise, ego, or a maybe-later thought, keep it out.

## another rule

your spec should reduce guessing.
it should not become a second source of chaos.

## last rule

if a question would materially change architecture, security, or user behavior, put it in **must ask before coding**.
if not, give the AI a safe default.
