# SPEC_EXAMPLE.md

## 1. project intent
build a tiny url shortener for solo builders.

this app should let a signed-in user paste a long url, get back a short link, and track basic click counts from a simple dashboard.

the first 5-minute win:
- sign in
- create a short link
- open it
- see the click count go up

## 2. stack
- frontend: Next.js
- backend: Next.js route handlers
- database: sqlite with drizzle
- auth: email magic link
- deployment: Vercel
- anything non-negotiable about the stack?: keep it cheap, simple, and deployable by one beginner

## 3. core features
- create a short link from a long url
- list your links in a dashboard
- show click counts per link
- allow deleting your own links

## 4. data / schema
- main entities:
  - users: id, email, created_at
  - links: id, user_id, slug, original_url, clicks, created_at
- important fields:
  - `slug` must be unique
  - `original_url` must be validated before save
  - `clicks` starts at 0 and increments on redirect
- relationships:
  - one user has many links
- what data must stay private?
  - user email addresses
  - any internal auth/session data

## 5. invariants
these rules stay true no matter how the code is structured.

- one-per-day rules:
  - not applicable here
- uniqueness rules:
  - every `slug` must be unique
- ownership rules:
  - users can only see and delete their own links
- deletion/reuse rules:
  - deleted slugs are not reused in v1
- counting / consistency rules:
  - every successful redirect increments click count exactly once in normal operation

## 6. views / screens / routes
- `/` landing page with link creation form and short explanation
- `/dashboard` signed-in page showing created links and click counts
- `/login` magic-link sign-in page
- `/:slug` redirect route

## 7. auth / permissions
- who can sign up?
  - anyone with a valid email address
- who can do what?
  - signed-in users can create, view, and delete their own links
- what must stay private?
  - emails, session state, and other users' links
- are there admin actions?
  - no admin panel in v1
- what should unauthenticated users be able to do?
  - view landing page only

## 8. constraints
- must use server-side validation for all mutations
- must not use a paid database for the MVP
- performance / cost constraints:
  - keep infra near-free for low traffic
- style / UX constraints:
  - plain, clean UI, no heavy design work
- scope limits for v1:
  - no teams
  - no billing
  - no custom domains
  - no advanced analytics

## 9. operational assumptions
- expected traffic / scale:
  - low traffic MVP
- hobby deploy acceptable?:
  - yes
- local file persistence acceptable?:
  - acceptable for demo/prototype only, not a promise of durable production persistence on Vercel
- region / latency assumptions:
  - single-region is fine for v1
- uptime / durability expectations:
  - hobby-grade MVP, not enterprise durability

## 10. decision defaults
if unspecified elsewhere, default to:

- routing default:
  - Next.js App Router
- deletion default:
  - hard delete
- date/time default:
  - UTC timestamps
- validation default:
  - allow only `http` and `https` urls
- error-handling default:
  - fail clearly, do not silently swallow route/mutation errors
- auth default:
  - use a standard email magic-link library/pattern, not a fake auth stub

## 11. non-goals / no silent substitutions
- do not replace auth with a fake local mock unless explicitly requested
- do not swap sqlite for a paid hosted database in v1 unless required and approved
- do not add social sharing, teams, billing, analytics dashboards, or admin systems
- do not quietly turn this into a link-in-bio tool or marketing product

## 12. do / don't
### do
- validate urls before saving
- enforce ownership checks on delete
- keep redirects fast and simple

### don't
- don't add social sharing features
- don't add admin panels
- don't add custom domains in v1

## 13. acceptance criteria
- [ ] a signed-in user can create a short link from the landing page
- [ ] visiting the short link redirects correctly
- [ ] click count increases after a redirect
- [ ] dashboard shows only that user's links
- [ ] deleting a link removes it from the dashboard
- [ ] unauthenticated users cannot create links
- [ ] user A cannot see or delete user B's links
- [ ] non-http/https urls are rejected

## 14. failure conditions
what would make this build a fail even if it mostly works?

- a user can see or delete another user's links
- the app accepts invalid urls without validation
- the redirect works but click counts never update
- the AI adds extra v1 features that complicate the app for no reason

## 15. open questions
- should slug generation be random or user-editable?
- should deleted links hard-delete or soft-delete later?
- should click counts update synchronously or through a background-safe pattern later?

### must ask before coding
- none for MVP if the defaults above are accepted

### safe defaults if unanswered
- random slug generation
- hard delete
- synchronous click increment on redirect
