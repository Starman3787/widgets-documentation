# Reference

Our API is a HTTPS/REST API.

#### Base URL

```text
https://widgets.gg/api
```

## Authentication

In order to access any sensitive parts of our API, you must provide authentication. This can be done by providing an `authorization` HTTP header, like so:

```text
authorization: TOKEN
```

Failing to provide authentication will result in a `401 Unauthorized` HTTP error response.

You can find your API token [here](https://widgets.gg/me/api).



