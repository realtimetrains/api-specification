# Realtime Trains API draft specification

This repository contains the implemented specification for the next generation of the Realtime Trains API.

[You can view a UI view of the specification here.](https://realtimetrains.github.io/api-specification/)

## Contributing

We welcome contributions, suggestions and change requests to this specification. Please suggest these via issues on the repository.

_Do not_ request changes through documentation changes via pull requests, these **will** be closed without review. 

## Access Control

API authentication is performed through a *Bearer* token authentication. You may either hold a long-life refresh or access token. When you are provided with the key, it will be made clear what you hold.

**It is a requirement that no token is placed in a downstream user application unless specifically authorised by us.** If we identify a token is in a downstream user application, it **will** be revoked.

End-user applications are expected to proxy their requests through a server-side application such that token is not available publicly.

### Long-life Access Token

If you hold a long-life access token, you do not need to refresh or update your token unless it reaches its expiry. You can request a new token by contacting the RTT Team at hello@realtimetrains.com.

### Refresh Token

If you have a refresh token, you will need to periodically request an access token. You can do this through the `/api/get_access_token` endpoint. This will issue you an access token that is valid until the time defined in `validUntil`. It will also tell you your entitlements.

### Understanding your entitlements

An access token does not grant access to all functionality of the API. Entitlements can restrict access to namespaces and/or functionality, such as access to detailed information or Know Your Train data.

When you have a valid access token, your entitlements can be found through the `/api/info` endpoint. 

## Getting an access token

We have recently launched the Realtime Trains unified login service. We will soon be relaunching our API portal which will provide access tokens.

More information will be provided when the API portal relaunches.

For users with access to endpoints at https://secure.realtimetrains.co.uk, you will be contacted individually.

## Versioning

The API is updated frequently and is versioned such that you can fix yourself to a defined version.

You can request a specific version of the API by either:
* sending a `Version` header in your HTTP request, or
* sending a `version` GET parameter in your HTTP URI.

If you do not send a version request, you will automatically receive the latest version of the API.

You can find the version identifier you are currently using on the `version` property in the `/api/info` endpoint.

## API Transition

We will transition to the new API versions as follows:

* https://api.rtt.io access will be kept available for at least 6 months
* https://secure.realtimetrains.co.uk (supported API) as follows:
  * Users who access this at no cost will be able to access this for 9 months
  * Commercial customers will be able to access this for 12 months

If you are not sure what category you are under, contact us at hello@realtimetrains.com.

We will advise EOL dates for each version of the API when we release the v2 API into production usage.

## Discussion

Discussion of these changes with the RTT Team can be made on our [Discord server](https://discord.gg/mh3Rm9g9rG) in the #rtt-api-ng channel.