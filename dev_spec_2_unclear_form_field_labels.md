# Unclear form field labels — dev spec
Site: nomadinternet.com · Priority 2 · High · Effort: Low (0.5-2 days)

## Problem
Form fields lack explicit labels, so visitors don't know what data is required before engaging.

## Evidence (from the live site)
> (see report)

## Current state
notes: Five form fields without visible labels.

## Required change
notes: Add explicit, visible labels above each field.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add explicit, visible labels above each field.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unclear_form_field_labels` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
