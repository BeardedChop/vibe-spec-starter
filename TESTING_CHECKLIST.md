# TESTING_CHECKLIST.md

use this after your AI says it's done.

don't grade the vibe.
grade the match between the build and the spec.

## spec compliance
- [ ] the build matches the project intent
- [ ] core features from `SPEC.md` actually exist
- [ ] constraints were followed
- [ ] the AI did not quietly add extra features
- [ ] acceptance criteria were checked one by one
- [ ] failure conditions were checked too

## implementation sanity
- [ ] auth behavior matches the spec
- [ ] validation exists on the server, not just the client
- [ ] permissions match the user roles in the spec
- [ ] routes/screens from the spec exist
- [ ] data/schema choices match the spec
- [ ] the "first 5-minute win" from the spec actually works

## red flags
- [ ] no fake placeholder data pretending to be real persistence
- [ ] no secrets in source
- [ ] no TODOs hiding core missing functionality
- [ ] no major feature skipped without explanation
- [ ] no major requirement was replaced by a simpler but wrong shortcut

## if it failed
- [ ] update the spec if the spec was weak
- [ ] update the implementation if the AI ignored a good spec
- [ ] note what the AI got wrong so the next version of the spec is stronger

## final question
- [ ] if i compare the build to `SPEC.md`, did the AI actually build what i asked for?
