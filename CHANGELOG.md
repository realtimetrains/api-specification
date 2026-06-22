# RTT API Changelog

This file covers changes to the API as well as the specification. The oldest changes are listed at the bottom. All versions prior to 2026-04-17 are not detailed.

## 2026-06-22
This release provides internal updates for our own functionality demands and provides no fixes or additional endpoints relevant for public use.

## 2026-06-20
This release *deprecates* the `/gb-nr/allocations_by_service` endpoint, and replaces it with a new `/gb-nr/allocations/by-service`. Entitlement requirements for this endpoint are unchanged.

There is a new `/gb-nr/allocations/by-class` endpoint, which allows searching by train class. This requires the same entitlements as `by-service` at present.

Adds a clarification that `/service` endpoints support the detailed query parameter.

## 2026-05-19
This release provides internal updates for our own functionality demands and provides no fixes or additional endpoints relevant for public use.

## 2026-04-30
* Fix issue with /data/locations_ungrouped where locations that were marked as associated internally were not being provided

## 2026-04-28
* Fix issue with platform 0s not showing if you don't hold any entitlements

## 2026-04-23
* Changes to the operator.name field to indicate that this should **not** be cached under any circumstances by keying against the code. We may change this field dynamically based on other data to reflect operator branding, rather than name.

Note: in a future change, we will likely revert this such that operator.name becomes the true operator name again, but add a brand key that should be used.

## 2026-04-22
* The authentication evaluators will now return an indication if they detect a token identity rather than the token itself
* Update backend handling of Know Your Train Data

This document previously noted a version 2026-04-20 but this was never released due to systems issues.

## 2026-04-17 
* Fix issue with pass objects showing with no reports when there are no pass timings
* Fix issue with partial cancellations on the day
* Fix issue when lifting rate limiting in only one dimension
* Fix API definition issues:
  * ORIGIN and DESTINATION are output as CALL.
  * PASS can appear as well as null.
  * Update the description of `realtimeEstimate`
* Add API authentication details to the OpenAPI spec as well
