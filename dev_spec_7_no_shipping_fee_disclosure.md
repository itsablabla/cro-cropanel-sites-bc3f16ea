# No shipping fee disclosure — dev spec
Site: nomadinternet.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Shipping costs are not mentioned, leaving a cost unknown until later in checkout.

## Evidence (from the live site)
> Prices shown on the page: $99.95/month $129.95/month $99.95/Mo $99.95/month $129.95/month $99.95
> Page copy reads “Existing Customers: [Pay Bill](https://nomadinternet.com/pages/pay-now) \| [Submit Ticket](mailto:support@nom”.

## Current state
notes: No shipping cost mentioned.

## Required change
notes: Display shipping cost or 'free shipping' badge.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display shipping cost or 'free shipping' badge.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_shipping_fee_disclosure` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
