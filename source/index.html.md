---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ

toc_footers:
  - <a class="signup" href='https://app.coldlead.io/register'>Get a free API key</a>

includes:
  - errors
  - rate-limiting
  - account
  - email-verifier
  - email-finder

search: true

code_clipboard: true
---

# Introduction

> API Endpoint

```shell
https://api.coldlead.io/v1/
```

Welcome to ColdLead.io's API! You can use this API to access all our API endpoints.

The API is organized around REST. All requests should be made over SSL. All request and response bodies, including errors, are encoded in JSON.

<!-- To play around with a few examples, we recommend a REST client called Postman. Simply tap the button below to import a pre-made collection of examples. -->

# Authentication

> To authorize, use this code:

```shell
curl "https://api.coldlead.io/v1/api_endpoint_here"
  -H "Accept: application/json"
  -H "Authorization: Bearer {key}"
```

Authentication is done via the API key which you can find in your [account settings](https://app.coldlead.io/settings#api-keys).

You will have to add your API Key to every call you make to our API. This parameter is always required. We'll return an error if the key is either missing or invalid.

Your API key is what identifies your account, so be sure to keep it secret! Please don’t share it with anyone outside of your organization.

`Authorization: Bearer myapikey`

<aside class="notice">
You must replace <code>myapikey</code> with your personal API key.
</aside>

