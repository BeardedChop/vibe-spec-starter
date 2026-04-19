# incomplete-spec-example.md

this is an intentionally incomplete spec.
it exists to teach when the AI should stop and ask questions instead of guessing.

## 1. project intent
build a small app for booking appointments.

## 2. stack
- frontend: Next.js
- backend: Next.js
- database: postgres
- auth:
- deployment: Vercel

## 3. core features
- users can book appointments
- users can manage appointments
- admin can see everything

## 4. data / schema
- appointments
- users

## 5. invariants
- 

## 6. views / screens / routes
- `/`
- `/dashboard`

## 7. auth / permissions
- who can sign up?
- who can do what?
- what must stay private?
- are there admin actions?
- what should unauthenticated users be able to do?

## 8. constraints
- make it simple

## 9. operational assumptions
- 

## 10. decision defaults
- 

## 11. non-goals / no silent substitutions
- 

## 12. do / don't
### do
- make it easy to use

### don't
- 

## 13. acceptance criteria
- [ ] appointments work

## 14. failure conditions
- 

## 15. open questions
- what kind of appointments?
- who counts as admin?
- how long are appointments?
- can users book overlapping slots?
- is payment involved?
- should unauthenticated users be able to browse availability?

### must ask before coding
- what auth model is required?
- what appointment constraints prevent double-booking?
- what permissions separate users from admins?
- is payment part of the MVP?

### safe defaults if unanswered
- none, because too many core decisions are missing

## why this is incomplete

an AI could build something from this.
that does not mean it should.

this spec is missing core security, scheduling, and product rules.
a good AI should pause here and ask questions before implementing.
