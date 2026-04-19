# bug-board-spec.md

## 1. project intent
build a tiny internal bug board for solo builders.

the user should be able to log bugs, set severity, move them between statuses, and filter the list quickly.

the first 5-minute win:
- create a bug
- mark it high severity
- move it from open to fixed

## 2. stack
- frontend: Next.js
- backend: Next.js route handlers
- database: sqlite with drizzle
- auth: simple password gate or local auth for v1
- deployment: Vercel
- anything non-negotiable about the stack?: keep setup simple enough for one person

## 3. core features
- create bug entries
- set severity
- change status
- filter by status or severity

## 4. data / schema
- main entities: bugs
- important fields: title, description, severity, status, created_at
- relationships: none needed for v1
- what data must stay private?: all bug content

## 5. views / screens / routes
- `/` main bug board
- `/new` create bug page or modal
- `/bugs/[id]` bug details view
- API routes for create/update/filter

## 6. auth / permissions
- who can sign up?: single internal user for v1
- who can do what?: the single user can manage all bugs
- what must stay private?: every bug entry
- are there admin actions?: no
- what should unauthenticated users be able to do?: nothing

## 7. constraints
- must use server-side validation for writes
- must not add comments, attachments, or team collaboration in v1
- performance / cost constraints: cheap enough for hobby deployment
- style / UX constraints: prioritize fast triage over pretty UI
- scope limits for v1: no notifications, no analytics, no assignment workflow

## 8. do / don't
### do
- keep status changes fast
- make severity obvious
- keep the board easy to scan

### don't
- don't add kanban drag-and-drop if it slows the MVP
- don't add multi-user support
- don't add file uploads

## 9. acceptance criteria
- [ ] user can create a bug entry
- [ ] user can change severity and status
- [ ] board can filter by status
- [ ] board can filter by severity

## 10. failure conditions
- filtering is broken or confusing
- status changes do not persist reliably
- the app adds team features that were explicitly excluded

## 11. open questions
- should status options be fixed or customizable?
- should description support markdown in v1?
