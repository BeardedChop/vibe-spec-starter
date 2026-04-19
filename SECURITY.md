# SECURITY.md

pre-flight checklist for anything generated from a spec.

## spec safety checks

- [ ] no secrets, tokens, or private keys written into `SPEC.md`
- [ ] auth requirements are explicit if auth exists
- [ ] permissions / roles are explicit if more than one user type exists
- [ ] validation rules are explicit for user input
- [ ] storage/database choice is named, not implied
- [ ] constraints clearly forbid dangerous shortcuts

## common AI failure modes

- AI invents fields or features not in the spec
- AI ignores auth or validation because the spec was vague
- AI adds client-side-only security for server problems
- AI treats examples as permission to hardcode data or secrets
- AI claims success without checking acceptance criteria

## before shipping a real app

- [ ] verify protected routes actually require auth
- [ ] verify server-side validation exists
- [ ] verify no secrets landed in source
- [ ] verify the built app matches the acceptance criteria
- [ ] verify the AI did not quietly skip hard parts

if any of those fail, stop and fix the spec or the implementation before shipping.
