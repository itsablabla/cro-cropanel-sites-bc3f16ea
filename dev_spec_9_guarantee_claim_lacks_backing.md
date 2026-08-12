# Guarantee claim lacks visible backing — dev spec
Site: nomadinternet.com · Priority 9 · Medium · Effort: Medium (2-5 days)

## Problem
The 'SHOP WITH CONFIDENCE' claim has no visible guarantee or return policy, leaving it unsupported at point of purchase.

## Evidence (from the live site)
> A section heading reads “SHOP WITH CONFIDENCE”.
> 5 distinct calls to action compete on the same page: “CHECK COVERAGE”, “Watch on”, “SEE WHAT I QUALIFY FOR”, “START CHAT”, “CHECK MY COVERAGE”.

## Current state
notes: No guarantee details visible.

## Required change
notes: Add visible money-back guarantee or return policy statement.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add visible money-back guarantee or return policy statement.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_guarantee_claim_lacks_backing` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
