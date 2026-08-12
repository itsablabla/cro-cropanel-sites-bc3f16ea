# Rural page title misleads destination — dev spec
Site: nomadinternet.com · Priority 8 · Medium · Effort: Medium (2-5 days)

## Problem
The page title 'How Nomad Internet Works - YouTube' does not match the page content, disorienting users mid-funnel.

## Evidence (from the live site)
> The browser title reads “How Nomad Internet Works - YouTube”.
> A section heading reads “Nomad Internet: The Go-To For Rural Internet”.

## Current state
notes: Page title is misleading.

## Required change
notes: Update title to reflect rural internet content.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Update title to reflect rural internet content.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_rural_page_title_misleads` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
