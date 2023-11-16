# Speakeasy Bar Starter SDK

<div align="left">
    <a href="https://speakeasyapi.dev/"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    
</div>

<br/>

This is a sample SDK generated for the Speakeasy Bar API. Have a look around and familiarize yourself with the Speakeasy Product!

When you're ready you can use this modify this repo to reference your own OpenAPI spec or go back to the Speakeasy app to complete onboarding and generate your first SDK!


## 🏗 **Welcome to your new SDK!** 🏗

It has been generated successfully based on your OpenAPI spec. However, it is not yet ready for production use. Here are some next steps:
- [ ] 🛠 Make your SDK feel handcrafted by [customizing it](https://www.speakeasyapi.dev/docs/customize-sdks)
- [ ] ♻️ Refine your SDK quickly by iterating locally with the [Speakeasy CLI](https://github.com/speakeasy-api/speakeasy)
- [ ] 🎁 Publish your SDK to package managers by [configuring automatic publishing](https://www.speakeasyapi.dev/docs/productionize-sdks/publish-sdks)
- [ ] ✨ When ready to productionize, delete this section from the README


### Local development

Once you have the SDK setup you may want to iterate on the SDK. Speakeasy supports OpenAPI vendor extensions that can be added to your spec to customize the SDK ergonomics (method names, namespacing resources etc.) and functionality (adding retries, pagination, multiple server support etc)

To get started install the Speakeasy CLI.

In your terminal, run:

```bash
brew install speakeasy-api/homebrew-tap/speakeasy
```
Once you annonate your spec with an extension you will want to run `speakeasy validate` to check the spec for correctness and `speakeasy generate` to recreate the SDK locally. More documentation on OpenAPI extensions [here](https://speakeasyapi.dev/docs/customize-sdks/namespaces/). Here's an example of adding a multiple server support to the spec so that your SDK supports production and sandbox versions of your API. The attached Makefile also attaches some helper commands.

```yaml
info:
  title: Example
  version: 0.0.1
servers:
  - url: https://prod.example.com # Used as the default URL by the SDK
    description: Our production environment
    x-speakeasy-server-id: prod
  - url: https://sandbox.example.com
    description: Our sandbox environment
    x-speakeasy-server-id: sandbox
```

Once you're finished iterating and happy with the output push only the latest version of spec into the repo and regenerate the SDK using step 6 above. 

<!-- Start SDK Installation -->
## SDK Installation

```bash
pip install git+https://github.com/speakeasy-sdks/chrislevn-sample-sdk.git
```
<!-- End SDK Installation -->

## SDK Example Usage
<!-- Start SDK Example Usage -->
### Example

```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    api_key="<YOUR_API_KEY>",
)


res = s.menu.drinks.list()

if res.classes is not None:
    # handle response
    pass
```
<!-- End SDK Example Usage -->

<!-- Start SDK Available Operations -->
## Available Resources and Operations



### [menu.drinks](docs/sdks/drinks/README.md)

* [list](docs/sdks/drinks/README.md#list) - Get a list of drinks
<!-- End SDK Available Operations -->

<!-- Start Dev Containers -->
# Dev Containers
<div align="left">
    <a href="https://codespaces.new/speakeasy-sdks/template-speakeasy-bar.git/tree/main"><img src="https://github.com/codespaces/badge.svg" /></a>
    
</div>

Experience our SDK in an enhanced sandbox environment. Try it now in **GitHub Codespaces**!

* [Explore Dev Containers](.devcontainer/README.md)
<!-- End Dev Containers -->

<!-- Start Error Handling -->
## Error Handling

Handling errors in this SDK should largely match your expectations.  All operations return a response object or raise an error.  If Error objects are specified in your OpenAPI Spec, the SDK will raise the appropriate Error type.

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 400-600         | */*             |

### Example

```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    api_key="<YOUR_API_KEY>",
)


res = None
try:
    res = s.menu.drinks.list()

except (errors.SDKError) as e:
    print(e) # handle exception


if res.classes is not None:
    # handle response
    pass
```
<!-- End Error Handling -->

<!-- Start Server Selection -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `server_idx: int` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| # | Server | Variables |
| - | ------ | --------- |
| 0 | `https://speakeasy.bar` | None |

#### Example

```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    server_idx=0,
    api_key="<YOUR_API_KEY>",
)


res = s.menu.drinks.list()

if res.classes is not None:
    # handle response
    pass
```


### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `server_url: str` optional parameter when initializing the SDK client instance. For example:
```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    server_url="https://speakeasy.bar",
    api_key="<YOUR_API_KEY>",
)


res = s.menu.drinks.list()

if res.classes is not None:
    # handle response
    pass
```
<!-- End Server Selection -->

<!-- Start Custom HTTP Client -->
## Custom HTTP Client

The Python SDK makes API calls using the (requests)[https://pypi.org/project/requests/] HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with a custom `requests.Session` object.

For example, you could specify a header for every request that this sdk makes as follows:
```python
import the_speakeasy_bar
import requests

http_client = requests.Session()
http_client.headers.update({'x-custom-header': 'someValue'})
s = the_speakeasy_bar.TheSpeakeasyBar(client: http_client)
```
<!-- End Custom HTTP Client -->

<!-- Start Go Types -->

<!-- End Go Types -->



<!-- Start Authentication -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name      | Type      | Scheme    |
| --------- | --------- | --------- |
| `api_key` | apiKey    | API key   |

To authenticate with the API the `api_key` parameter must be set when initializing the SDK client instance. For example:
```python
import the_speakeasy_bar

s = the_speakeasy_bar.TheSpeakeasyBar(
    api_key="<YOUR_API_KEY>",
)


res = s.menu.drinks.list()

if res.classes is not None:
    # handle response
    pass
```
<!-- End Authentication -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically.
Feel free to open a PR or a Github issue as a proof of concept and we'll do our best to include it in a future release!

### SDK Created by [Speakeasy](https://docs.speakeasyapi.dev/docs/using-speakeasy/client-sdks)
