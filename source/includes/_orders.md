# Orders

## Validate Order

```shell
curl -X "POST" "https://api.mbctestweb.com/v1/orders/validate" \
     -H 'API_KEY: qe7Rz6/7HI01HBfTQGqceADLG8fEfySc9jrTw9HYTZc=' \
     -H 'Content-Type: application/json' \
     -d $'{
  "license_plate": "PNOTR",
  "obligation_id": 118354,
  "bond_amount": 5000,
  "principal_name": "Construction Company, Inc.",
  "principal_address1": "515 Oak Drive",
  "principal_city": "Urbandale",
  "principal_state": "IA",
  "principal_zip": "50322",
  "effective_date": "2017-11-07",
  "expiration_date": "2021-11-07"
  "attorney_in_fact": "John Wolf",
  "producer_name": "Bill Billings",
  "state": "IA",
  }'
```

> JSON response, when successful:

```json
{
  "success": true,
  "valid":true
}
```

> JSON response, when unsuccessful:

```json
{
	"success": false,
	"valid": false,
	"errors": {
		"bond_amount": [
			"can't be blank",
			"is not a valid bond amount for obligation. Valid amounts are 5000"
		]
	}
}
```

This endpoint determines whether or not your Order information is valid.


### HTTP Request

`POST https://api.merchantsbonding.com/v1/orders/validate`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
`license_plate` | yes | a string containing the "license plate", e.g. PNEOG (obtained from obligations end point)
`obligation_id` | yes | a number identifying the obligation to be used (obtained from obligations endpoint)
`obligee_name` | no | a string containing an obligee name (for obligee-specific premiums)
`bond_amount` | yes | a number representing the bond amount in cents
`principal_name` | yes | a string containing the principal's name
`principal_address1` | yes | a string containing the first line of the principal's address
`principal_address2` | no | a string containing the second line of the principal's address
`principal_city` | yes | a string containing principal's the city
`principal_state` | yes | a string containing the principal's two-character state code
`principal_zip` | yes | a string containing the principal's ZIP Code
`effective_date` | yes | a string containing the effective date of the bond, formatted `yyyy-mm-dd`
`expiration_date` | yes | a string containing the expiration date of the bond, formatted `yyyy-mm-dd`
`attorney_in_fact` | yes | a string containing the attorney-in-fact
`producer_name` | yes | a string containing the producer's name
`state` | yes | a string containing the two-character state code for the obligation

## Retrieve an Order

```shell
curl -X "GET" "https://api.mbctestweb.com/v1/orders/1"
```

> JSON response, when successful:

```json
{
	"success": true,
	"order": {
		"bond_number": "AZ5105756",
		"premium":2500,
		"principal": {
			"name": "Construction Company, Inc.",
			"address1": "515 Oak Drive",
			"address2": null,
			"city": "Urbandale",
			"state": "IA",
			"zip": "50322"
		},
		"documents":[
			{
				"filename": "Bond.pdf",
				"url": "https://example.com/Bond.pdf"
			}
		]
	}
}
```

> JSON response, when unsuccessful:

```json
{
	"success": false
}
```

This endpoint allows you to retrieve a single Order.

### HTTP Request

`GET https://api.merchantsbonding.com/v1/orders/1`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
`id` | yes | a number representing the Order's ID

## Create Order

```shell
curl -X "POST" "https://api.mbctestweb.com/v1/orders" \
     -H 'API_KEY: qe7Rz6/7HI01HBfTQGqceADLG8fEfySc9jrTw9HYTZc=' \
     -H 'Content-Type: application/json' \
     -d $'{
  "license_plate": "PNOTR",
  "obligation_id": 118354,
  "bond_amount": 5000,
  "principal_name": "Construction Company, Inc.",
  "principal_address1": "515 Oak Drive",
  "principal_city": "Urbandale",
  "principal_state": "IA",
  "principal_zip": "50322",
  "effective_date": "2017-11-07",
  "expiration_date": "2021-11-07"
  "attorney_in_fact": "John Wolf",
  "producer_name": "Bill Billings",
  "state": "IA",
  }'
```

> JSON response, when successful:

```json
{
	"success": true,
	"order": {
		"bond_number": "AZ5105756",
		"premium":2500,
		"principal": {
			"name": "Construction Company, Inc.",
			"address1": "515 Oak Drive",
			"address2": null,
			"city": "Urbandale",
			"state": "IA",
			"zip": "50322"
		},
		"documents":[
			{
				"filename": "Bond.pdf",
				"url": "https://example.com/Bond.pdf"
			}
		]
	}
}
```

> JSON response, when unsuccessful:

```json
{
	"success": false,
	"errors": {
		"bond_amount": [
			"can't be blank",
			"is not a valid bond amount for obligation. Valid amounts are 5000"
		]
	}
}
```

This endpoint allows you to create an Order.

### HTTP Request

`POST https://api.merchantsbonding.com/v1/orders`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
`license_plate` | yes | a string containing the "license plate", e.g. PNEOG (obtained from obligations end point)
`obligation_id` | yes | a number identifying the obligation to be used (obtained from obligations endpoint)
`obligee_name` | no | a string containing an obligee name (for obligee-specific premiums)
`bond_amount` | yes | a number representing the bond amount in cents
`principal_name` | yes | a string containing the principal's name
`principal_address1` | yes | a string containing the first line of the principal's address
`principal_address2` | no | a string containing the second line of the principal's address
`principal_city` | yes | a string containing principal's the city
`principal_state` | yes | a string containing the principal's two-character state code
`principal_zip` | yes | a string containing the principal's ZIP Code
`effective_date` | yes | a string containing the effective date of the bond, formatted `yyyy-mm-dd`
`expiration_date` | yes | a string containing the expiration date of the bond, formatted `yyyy-mm-dd`
`attorney_in_fact` | yes | a string containing the attorney-in-fact
`producer_name` | yes | a string containing the producer's name
`state` | yes | a string containing the two-character state code for the obligation
