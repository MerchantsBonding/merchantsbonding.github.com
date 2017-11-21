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
  "obligations": [
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
      "name":"Notary Public Errors & Omissions Policy",
      "license_plate":"PNEO",
      "bond_amounts":[1000,3000,5000],
      "term_length":4
    }
  ]
}
```

This endpoint retrieves all Obligations.

### HTTP Request

`GET https://api.merchantsbonding.com/v1/obligations`

### Query Parameters

None.
