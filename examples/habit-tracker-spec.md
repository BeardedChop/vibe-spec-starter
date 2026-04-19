# habit-tracker-spec.md

## 1. project intent
build a tiny habit tracker for one person.

the user should be able to create habits, mark them complete for the day, and see a simple streak count.

the first 5-minute win:
- create one habit
- mark it complete
- see the streak update

## 2. stack
- frontend: Next.js
- backend: Next.js route handlers
- database: sqlite
- auth: none for v1, single-user local app
- deployment: Vercel
- anything non-negotiable about the stack?: keep it dead simple and cheap

## 3. core features
- create a habit
- mark a habit complete for today
- view current streak per habit
- archive a habit

## 4. data / schema
- main entities: habits, completions
- important fields: habit name, created_at, archived_at, completion_date
- relationships: one habit has many completions
- what data must stay private?: all habit history stays private to the single user

## 5. views / screens / routes
- `/` dashboard with habit list
- `/new` create habit form
- `/archive` archived habits view
- API routes for habit create/update/archive

## 6. auth / permissions
- who can sign up?: nobody, single-user local app in v1
- who can do what?: the single user can manage all habits
- what must stay private?: the whole dataset
- are there admin actions?: no
- what should unauthenticated users be able to do?: not relevant in v1

## 7. constraints
- must use server-side validation for writes
- must not add social features, teams, or reminders in v1
- performance / cost constraints: near-zero cost
- style / UX constraints: clean and boring beats pretty and confusing
- scope limits for v1: no charts, no gamification system

## 8. do / don't
### do
- keep completion logging simple
- show streak clearly
- keep habit creation fast

### don't
- don't add calendar heatmaps in v1
- don't add sharing features
- don't add push notifications

## 9. acceptance criteria
- [ ] user can create a habit
- [ ] user can mark it complete for today
- [ ] streak increases after completion
- [ ] archived habits disappear from the main list

## 10. failure conditions
- streak math is unreliable
- archive does not actually remove habits from active view
- the app adds extra tracking features that slow down the core flow

## 11. open questions
- should users be allowed to backfill missed days?
- should habits reset streak immediately or after the day ends?
