# No guarantee or return policy — dev spec
Site: example.com · Priority 4 · Medium · Effort: Medium (2-5 days)

## Problem
The absence of any guarantee or return policy leaves visitors uncertain about risk, hindering conversion.

## Evidence (from the live site)
> Page copy reads “# Example Domain This domain is for use in documentation examples without needing permission. Avoid use in operations. [Learn more](https://iana.org/domains/example)”.

## Current state
h1: Example Domain; cta: Learn more; notes: No guarantee or return policy mentioned.

## Required change
h1: Example Domain; cta: Learn more; notes: Publish clear guarantee or return policy near CTA.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Publish clear guarantee or return policy near CTA.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_guarantee_or_return_policy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
