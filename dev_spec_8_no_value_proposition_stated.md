# No value proposition stated — dev spec
Site: example.com · Priority 8 · High · Effort: Low (0.5-2 days)

## Problem
The page copy fails to communicate what is being sold or why it is valuable, leaving visitors without a reason to engage.

## Evidence (from the live site)
> This domain is for use in documentation examples without needing permission.
> Avoid use in operations.

## Current state
h1: Example Domain; cta: Learn more; notes: Generic example-domain copy with no product or service description.

## Required change
h1: Clear value proposition naming product/service and key benefit; cta: Benefit-oriented CTA; notes: Replace generic copy with specific value proposition.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace generic copy with specific value proposition.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_value_proposition_stated` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
