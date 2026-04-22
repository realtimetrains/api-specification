# RTT API Changelog

This file covers changes to the API as well as the specification. The oldest changes are listed at the bottom. All versions prior to 2026-04-17 are not detailed.

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
