# American Cloud Python SDK

Typed Python client for the [American Cloud](https://americancloud.com) public API.

This SDK is auto-generated from the OpenAPI specification using [Fern](https://buildwithfern.com). It targets American Cloud API **`v1`** — see [`VERSIONING.md`](./VERSIONING.md) for how SDK releases track the API.

![Listing regions and VMs with the American Cloud Python SDK](https://raw.githubusercontent.com/American-Cloud/americancloud-sdk-python/master/.demo/sdk-firstcall-python.gif)

## Installation

```sh
pip install americancloud
```

## Authentication

Every request requires **both** parts of an American Cloud API key, sent as headers:

| Header | SDK option |
|---|---|
| `X-API-Client-ID` | `api_key` |
| `X-API-Client-Secret` | `api_client_secret` |

Create and manage keys at **[console.americancloud.com/api-keys](https://console.americancloud.com/api-keys)**. The client secret is shown once at creation — store it securely. If lost, revoke the key and create a new one.

Each key is scoped at creation:

- **`read-only`** — `GET` endpoints only
- **`read-write`** — full access to all resource management endpoints

## Quick start

### Synchronous

```python
import os
from americancloud import AmericancloudApi

client = AmericancloudApi(
    api_key=os.environ["AMERICANCLOUD_API_CLIENT_ID"],
    api_client_secret=os.environ["AMERICANCLOUD_API_CLIENT_SECRET"],
)

vms = client.vms.list_vms()
print(vms)
```

### Asynchronous

```python
import asyncio
import os
from americancloud import AsyncAmericancloudApi

async def main():
    client = AsyncAmericancloudApi(
        api_key=os.environ["AMERICANCLOUD_API_CLIENT_ID"],
        api_client_secret=os.environ["AMERICANCLOUD_API_CLIENT_SECRET"],
    )
    vms = await client.vms.list_vms()
    print(vms)

asyncio.run(main())
```

The client is namespaced by resource — `client.vms`, `client.block_storage`, `client.kubernetes`, `client.dns_zones`, etc.

## API endpoint

The SDK targets the American Cloud production API at **`https://api.americancloud.com`** by default. To override (e.g. for a self-hosted or internal environment), pass `base_url`:

```python
client = AmericancloudApi(
    api_key="...",
    api_client_secret="...",
    base_url="https://your-custom-endpoint.example.com",
)
```

## API reference

- **Full reference + code samples**: [americancloud.docs.buildwithfern.com](https://americancloud.docs.buildwithfern.com)
- **Interactive Swagger UI**: [api.americancloud.com/api-v1](https://api.americancloud.com/api-v1)

## Guides

Narrative walkthroughs on the American Cloud docs site:

- [Python SDK quickstart](https://americancloud.com/docs/sdks/python) — install, authenticate, estimate cost, then create a VM (sync and async), with error handling and pagination
- [SDKs & Terraform overview](https://americancloud.com/docs/sdks/overview) — when to reach for an SDK, Terraform, or the MCP server
- [Deploy with AI](https://americancloud.com/docs/deploy-with-ai/overview) — let an AI assistant build and ship to American Cloud

## Versioning

The SDK version **matches the API platform version it was generated from** — SDK `x.y.z` is generated from OpenAPI document `x.y.z`, so the SDK↔API mapping is one-to-one by construction:

- **Patch / minor** releases are backward-compatible — safe to upgrade.
- **Major** releases track a new API URL version (`/api/v2`) and may require code changes; check the [`CHANGELOG`](./CHANGELOG.md) first.
- The `1.x` line targets API `v1`, which remains available for at least six months after a `v2` release.
- Additive API changes (new endpoints, optional fields, enum values) ship within a version — tolerate unknown fields and new enum values gracefully.

See [`VERSIONING.md`](./VERSIONING.md) for the full policy.

## Reporting issues

Open an issue against this repository, or contact American Cloud support.

## Contributing

This SDK is generated — do not edit the source by hand. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the generation workflow.
