# Ambiguous form submit label — dev spec
Site: nomadinternet.com · Priority 3 · Medium · Effort: Low (0.5-2 days)

## Problem
The CONTINUE button label does not set expectations for the next step, adding cognitive effort at conversion.

## Evidence (from the live site)
> (see report)

## Current state
cta: CONTINUE; notes: Submit button reads CONTINUE.

## Required change
cta: Check My Coverage; notes: Replace with descriptive action.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace with descriptive action.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_ambiguous_form_submit_label` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
