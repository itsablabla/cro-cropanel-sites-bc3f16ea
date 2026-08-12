# Repeated identical form instances — dev spec
Site: nomadinternet.com · Priority 5 · Medium · Effort: Medium (2-5 days)

## Problem
Two identical CONTINUE forms on each page create confusion about which to complete, increasing abandonment.

## Evidence (from the live site)
> (see report)

## Current state
notes: Duplicate forms per page.

## Required change
notes: Consolidate into a single coverage-check form per page.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Consolidate into a single coverage-check form per page.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_repeated_identical_forms` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
