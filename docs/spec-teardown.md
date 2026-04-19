# spec teardown

this file explains why the spec template is shaped the way it is.

## 1. project intent

this stops the AI from solving the wrong problem.
if you cannot say what the product is for, the AI will improvise.

## 2. stack

stack choices remove a huge amount of guesswork.
if you leave this vague, the AI may pick tools you never wanted.

## 3. core features

this is the actual product scope.
not every dream you have for later. just the features that must exist now.

## 4. data / schema

if data relationships are fuzzy, implementation gets weird fast.
this section forces clarity around what exists and what connects to what.

## 5. views / screens / routes

this keeps the AI from inventing random screens or skipping obvious ones.

## 6. auth / permissions

this is where a lot of AI builds quietly break.
if roles and privacy are vague, the AI usually guesses wrong.

## 7. constraints

constraints are where you stop the AI from becoming "helpfully" destructive.
this is where you lock scope, stack, cost, and non-negotiables.

## 8. do / don't

this section is the fast-lane version of your preferences.
short, explicit, hard to miss.

## 9. acceptance criteria

this is the difference between "looks good" and "actually done."
if you cannot test it, it is not done.

## 10. failure conditions

this is underrated.
it tells the AI what would count as a fail even if the app kind of works.
that catches a lot of fake-complete output.

## 11. open questions

this keeps uncertainty visible.
open questions should trigger follow-up questions, not silent guessing.

## the real point

a spec is not paperwork.
it is compressed decision-making.
it gives the AI less room to be creative in the wrong direction.
