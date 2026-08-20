# No trust signals present — dev spec
Site: example.com · Priority 2 · High · Effort: Medium (2-5 days)

## Problem
The page lacks any trust indicators such as reviews, guarantees, or security badges, undermining visitor confidence.

## Evidence (from the live site)
> The page's main headline reads “Example Domain”.
> The only call to action on the page is “Learn more”.
> Page copy reads “# Example Domain This domain is for use in documentation examples without needing permission. Avoid use in operations. [Learn more](https://iana.org/domains/example)”.

## Current state
h1: Example Domain; cta: Learn more; notes: No trust elements present.

## Required change
h1: Example Domain; cta: Learn more; notes: Add testimonials, guarantee, or security badges near CTA.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add testimonials, guarantee, or security badges near CTA.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_trust_signals_present` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
