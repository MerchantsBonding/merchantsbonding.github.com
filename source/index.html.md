---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://merchantsbonding.com'>Merchants Bonding Company</a>

includes:
  - errors

search: true
---

# Introduction

Merchants Bonding API.

# Authentication

Merchants Bonding uses API keys to allow access to the API.

Our API expects for the API key to be included in all API requests to the server in a header that looks like the following:

`API_KEY: keykeykeykey`

# Obligations

## Get All Obligations

```shell
curl "https://api.merchantsbonding.com/v1/obligations"
  -H API_KEY:keykeykey
```

> JSON response:

```json
{
  "success":true,
  "obligations":
    [
      {
        "id":136880,
        "state":"TX",
        "name":"PRE-EXECUTED $10,000 Notary Public Bond",
        "license_plate":"PNOTR",
        "bond_amounts":[10000],
        "term_length":4
      },
      {
        "id":140334,
        "state":"CA",
        "name":"Notary Public Errors \u0026 Omissions Policy",
        "license_plate":"PNEO",
        "bond_amounts":[1000,3000,5000],
        "term_length":4
      }
```

This endpoint retrieves all Obligations.

### HTTP Request

`GET https://api.merchantsbonding.com/v1/obligations`

### Query Parameters

None.
