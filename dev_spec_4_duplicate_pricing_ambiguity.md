# Duplicate pricing creates comparison ambiguity — dev spec
Site: nomadinternet.com · Priority 4 · Medium · Effort: Medium (2-5 days)

## Problem
The same plan prices appear twice with different formatting, causing ambiguity about which price applies to which tier.

## Evidence (from the live site)
> A section heading reads “$99.95 /month”.
> A section heading reads “$129.95 /month”.
> Prices shown on the page: $99.95 /month $129.95 /month $99.95/mo $0.00 $99.95 $99.99

## Current state
notes: Duplicate pricing display on plans pages.

## Required change
notes: Consolidate pricing display to a single consistent format per plan tier.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Consolidate pricing display to a single consistent format per plan tier.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_pricing_ambiguity` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
