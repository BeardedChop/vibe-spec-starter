# reviewer rubric

use this when checking whether a spec is strong enough before you build.

## 1. product clarity
- can you tell what the app actually does?
- can you tell who it is for?
- is the first user win obvious?

## 2. scope control
- are the main features named?
- are non-goals clear?
- is v1 scope protected from feature creep?

## 3. security / ownership clarity
- are auth rules clear?
- are permissions clear?
- is private data named?
- are ownership boundaries explicit?

## 4. implementation safety
- are decision defaults present?
- are must-ask questions separated from safe defaults?
- are invariants present?
- are operational assumptions realistic?

## 5. testability
- are acceptance criteria observable?
- are failure conditions meaningful?
- could a reviewer compare the build against the spec without guessing?

## scoring
- 5/5: ship-ready spec
- 4/5: strong, minor ambiguity
- 3/5: workable, but AI will still guess important things
- 2/5: weak, should be tightened before implementation
- 1/5: too vague, AI should not build from this yet
