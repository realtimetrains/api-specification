# Realtime Trains API draft specification

This repository contains the draft specification for the next generation of the Realtime Trains API.

**This specification is not final** and may contain details that are not implemented within the API.

[You can view a UI view of the specification here.](https://realtimetrains.github.io/api-specification/)

## Contributing

We welcome contributions, suggestions and change requests to this specification. Please suggest these via issues on the repository.

_Do not_ request changes through documentation changes via pull requests, these **will** be closed without review. 

## Access Control

We have recently launched the Realtime Trains unified login service. It is likely that we will migrate the API portal to use this service.

The API itself will move from a *Basic* auth to a *Bearer* auth. We will issue access tokens from which you will need to request refresh tokens to access the API.

The exact mechanisms are yet to be defined.

## Versioning

We will release updates to the API frequently following initial implementation. 

Versioning is currently TBC, but our current thoughts are to use a HTTP header to request versions, and a default version can be selected within the portal.

## Transition

When this API specification is finalised and we complete implementation work to deliver it, we will transition the v1 APIs as follows:

* https://api.rtt.io access will be kept available for at least 6 months
* https://secure.realtimetrains.co.uk (supported API) as follows:
  * Users who access this at no cost will be able to access this for 9 months
  * Commercial customers will be able to access this for 12 months

If you are not sure what category you are under, contact us at hello@realtimetrains.com.

## Discussion

Discussion of these changes with the RTT Team can be made on our [Discord server](https://discord.gg/mh3Rm9g9rG) in the #rtt-api-ng channel.