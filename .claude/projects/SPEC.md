# SPEC.md

use short, concrete answers.
if something matters, write it.
if you do not care, leave it out.

## 1. project intent
- what are you building?
- who is it for?
- what exact job should it do well?
- what should the user be able to do in the first 5 minutes?

## 2. stack
- frontend:
- backend:
- database:
- auth:
- deployment:
- anything non-negotiable about the stack?

## 3. core features
- feature 1:
- feature 2:
- feature 3:
- feature 4:

## 4. data / schema
- main entities:
- important fields:
- relationships:
- what data must stay private?

## 5. invariants
these are rules that must stay true even when the implementation changes.

- one-per-day rules:
- uniqueness rules:
- ownership rules:
- deletion/reuse rules:
- counting / consistency rules:

## 6. views / screens / routes
- route 1:
- route 2:
- route 3:
- route 4:

## 7. auth / permissions
- who can sign up?
- who can do what?
- what must stay private?
- are there admin actions?
- what should unauthenticated users be able to do?

## 8. constraints
- must use:
- must not use:
- performance / cost constraints:
- style / UX constraints:
- scope limits for v1:

## 9. operational assumptions
- expected traffic / scale:
- hobby deploy acceptable?:
- local file persistence acceptable?:
- region / latency assumptions:
- uptime / durability expectations:

## 10. decision defaults
if you do not specify something elsewhere, the AI should default to:

- routing default:
- deletion default:
- date/time default:
- validation default:
- error-handling default:
- auth default:

## 11. non-goals / no silent substitutions
- what should the AI NOT quietly swap in or add?
- example: do not replace real auth with a fake local stub unless explicitly allowed
- example: do not add extra features just because they seem useful

## 12. do / don't
### do
- 
- 
- 

### don't
- 
- 
- 

## 13. acceptance criteria
write outcomes that can be checked.
not vibes. not intentions.

- [ ] 
- [ ] 
- [ ] 
- [ ] 

## 14. failure conditions
what would make you reject this build even if it "mostly works"?

- 
- 

## 15. open questions
- what is still undecided?
- what choices should be postponed instead of guessed?

### must ask before coding
- 
- 

### safe defaults if unanswered
- 
- 
