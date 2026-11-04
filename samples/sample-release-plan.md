# Release Plan: Lab Results Portal v2.1

**Owner:** Delivery Lead, Digital Lab Systems
**Version:** 0.3 draft

## Purpose

This plan covers the release of version 2.1 of the Lab Results Portal, which adds bulk export of results to CSV and a new search filter.

## Scope

In scope: bulk export feature, search filter, minor bug fixes (12 tickets).
Out of scope: mobile app changes.

## Schedule

- Code freeze: 10 November
- UAT: 11–14 November
- Go-live: Saturday 16 November, 08:00–12:00

## Deployment steps

1. Put portal in maintenance mode.
2. Deploy new build through the pipeline to production.
3. Run database migration script.
4. Smoke test the home page and login.
5. Remove maintenance mode.

## Testing

UAT will be done by two lab managers. Automated regression tests run in the pipeline.

## Approvals

The release will be approved by the Delivery Lead.

## Communication

An email will go to all portal users on the Friday before go-live.

## Risks

- Database migration may take longer than expected.
