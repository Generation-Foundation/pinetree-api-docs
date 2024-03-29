# Pinetree API v0.1.0

## Test | Ping

`GET`
```
https://api.pinetree.space/ping
```

Success 200
```json
{
    "message": "ping"
}
```

## User | nonce (Authentication)

| Field | Type | Description |
|-------|------|----------------|
| user | string | Ethereum address |

`GET`
```
https://api.pinetree.space/user/:user/nonce
```

Success 200
```json
{
    "nonce": "I want to login on Pinetree at Thu Jun 23 2022 04:43:47 GMT+0000 (Coordinated Universal Time) 36cb"
}
```

## User | signature (Authentication)
- How to get the signature value?(https://blog.devgenius.io/authenticating-users-to-your-web-app-using-metamask-and-nodejs-e920e45e358)

| Field | Type | Description |
|-------|------|----------------|
| signature | string | Signature is a hex string signed by web3 sign method. |

`POST`
```
https://api.pinetree.space/user/:user/signature/:signature
```

Success 200
```json
{
    "message": "success",
    "user": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "token": "exJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0eXBlIjoidXNlciIsImFjY291bnQiOiJiZW5AYmFvYmFicGFydG5lcnMuaW8iLCJpYXQiOjE2NTQxNTg4MTMsImV4cOI6MTY1NDI0NTIxMywiaXNzIjoiQmFvYmFiIFBhcnRuZXJzIn0.F5rAb_JGhDiq5z8ZnpDMw9Gtf8V_-DsrTqM8j5La5AB"
}
```

## Wallet | Balance

- Required Auth Token

| Field | Type | Description |
|-------|------|----------------|
| tokenAddress | string | ERC20 contract address. If you input 'eth' or 'bgen', it will return ETH or bgen balance. |

`GET`
```
https://api.pinetree.space/wallet/token/:tokenAddress/balance
```

Success 200
```json
{
	"name": "GEN",
	"symbol": "GEN",
	"decimals": "18",
	"balance": "1000.000000000000000000"
}
```

## Wallet | my NFT

- Required Auth Token

`GET`
```
https://api.pinetree.space/wallet/nft
```

Success 200
```json
[
  {
    "id": 11,
    "project": "NFT Craft Test",
    "nft_owner": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "token_id": 1,
    "on_sale": "1",
    "on_chain": "0",
    "chain_name": "pinetree",
    "token_id_on_chain": "",
    "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Example #1\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
  },
  {
    "id": 12,
    "project": "NFT Craft333",
    "nft_owner": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "token_id": 1,
    "on_sale": "1",
    "on_chain": "0",
    "chain_name": "pinetree",
    "token_id_on_chain": "",
    "data": "[{\"description\":\"This is an example #2\",\"name\":\"NFT Craft 333333333\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
  }
]
```

## Wallet | user NFT

| Field | Type | Description |
|-------|------|----------------|
| address | string | Ethereum address. |

`GET`
```
https://api.pinetree.space/wallet/nft/:address
```

Success 200
```json
[
  {
    "id": 11,
    "project": "NFT Craft Test",
    "nft_owner": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "token_id": 1,
    "on_sale": "1",
    "on_chain": "0",
    "chain_name": "pinetree",
    "token_id_on_chain": "",
    "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Example #1\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
  },
  {
    "id": 12,
    "project": "NFT Craft333",
    "nft_owner": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "token_id": 1,
    "on_sale": "1",
    "on_chain": "0",
    "chain_name": "pinetree",
    "token_id_on_chain": "",
    "data": "[{\"description\":\"This is an example #2\",\"name\":\"NFT Craft 333333333\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
  }
]
```

## Project | create

- Required Auth Token

| Field | Type | Description |
|-------|------|----------------|
| projectName | string | English and number. No special symbol. |

`POST`
```
https://api.pinetree.space/project/:projectName/create
```

Success 200
```json
{
    "message": "success",
    "project": "NFT Craft",
    "project_owner": "0xedec843ee5ecdbf54ae7f25cf466d944375860e4",
    "gen_deposit": 0,
    "nft_total": 0
}
```

## Project | project

`GET`
```
https://api.pinetree.space/project/:projectName
```

Success 200
```json
{
    "project": "NFT Craft",
    "project_owner": "0xedec843ee5ecdbf54ae7f25cf466d944375860e4",
    "gen_deposit": 0,
    "nft_total": 0,
    "created_timestamp": 1655371419
}
```

## Project | latest projects

`GET`
```
https://api.pinetree.space/project/latest
```

Success 200
```json
[
  {
    "account": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "project": "NFT Craft Test",
    "created_timestamp": 1655371419
  },
  {
    "account": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "project": "NFT Craft222",
    "created_timestamp": 1655796848
  },
  {
    "account": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "project": "NFT Craft333",
    "created_timestamp": 1655796870
  },
  {
    "account": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
    "project": "testname",
    "created_timestamp": 1655948489
  }
]
```

## NFT | mint

- Required Auth Token

| Field | Type | Description |
|-------|------|----------------|
| projectName | string | English and number. No special symbol. |
| receiver | string | Receiver's Ethereum address |

`POST`
```
https://api.pinetree.space/project/:projectName/nft/mint/receiver/:receiver
```

Request Json Body
```json
{
  "royalty_fee": 0.025,
  "data": [
    {
      "description": "This is an example #1",
      "name": "NFT Example #1",
      "attributes": [
        {
          "trait_type": "color",
          "value": "red"
        },
        {
          "trait_type": "reveal",
          "value": "1654677698"
        }
      ],
      "image": "https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg",
      "animation_url": "",
      "background_color": "",
      "youtube_url": "",
      "external_url": ""
    }
  ]
}
```

Success 200
```json
{
  "message": "success",
  "project": "NFT Craft",
  "receiver": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
  "token_id": 467,
  "royalty_fee": 0.025,
  "on_sale": false,
  "chain": {
    "on_chain": false,
    "chain_name": "pinetree",
    "token_id_on_chain": 467
  }
}
```

## NFT | tokenId

| Field | Type | Description |
|-------|------|----------------|
| tokenId | number | NFT token id |

`GET`
```
https://api.pinetree.space/project/:projectName/nft/tokenId/:tokenId
```

Success 200
```json
{
  "project": "NFT Craft",
  "nft_owner": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
  "token_id": 467,
  "royalty_fee": 0.025,
  "on_sale": false,
  "chain": {
    "on_chain": false,
    "chain_name": "pinetree",
    "token_id_on_chain": 467
  },
  "data": [
    {
      "description": "This is an example #1",
      "name": "NFT Example #1",
      "attributes": [
        {
          "trait_type": "color",
          "value": "red"
        },
        {
          "trait_type": "reveal",
          "value": "1654677698"
        }
      ],
      "image": "https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg",
      "animation_url": "",
      "background_color": "",
      "youtube_url": "",
      "external_url": ""
    }
  ]
}
```

## Marketplace | order

`GET`
```
https://api.pinetree.space/marketplace/order?limit=10&orderBy=createdDate&orderDirection=desc
```

Success 200
```json
{
  "orders": [
    {
      "order_id": 16,
      "project": "NFT Craft333",
      "token_id": 5,
      "payment_token_symbol": "gen",
      "maker": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
      "taker": "",
      "submitted_at": 1655802215,
      "order_price": 350,
      "maker_fee": 0.025,
      "taker_fee": 0,
      "royalty_fee": 0.025,
      "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Craft 333333333\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
    },
    {
      "order_id": 12,
      "project": "NFT Craft333",
      "token_id": 1,
      "payment_token_symbol": "gen",
      "maker": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
      "taker": "",
      "submitted_at": 1655797156,
      "order_price": 250,
      "maker_fee": 0.025,
      "taker_fee": 0,
      "royalty_fee": 0,
      "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Craft 333333333\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
    },
    {
      "order_id": 11,
      "project": "NFT Craft Test",
      "token_id": 1,
      "payment_token_symbol": "gen",
      "maker": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
      "taker": "",
      "submitted_at": 1655792303,
      "order_price": 15.54205,
      "maker_fee": 0.025,
      "taker_fee": 0,
      "royalty_fee": 0,
      "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Example #1\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
    }
  ]
}
```

## Marketplace | order id

| Field | Type | Description |
|-------|------|----------------|
| orderId | number | NFT order id on marketplace |

`GET`
```
https://api.pinetree.space/marketplace/order/:orderId
```

Success 200
```json
{
  "order_id": 16,
  "project": "NFT Craft333",
  "token_id": 5,
  "payment_token_symbol": "gen",
  "maker": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
  "taker": "",
  "submitted_at": 1655802215,
  "order_price": 350,
  "maker_fee": 0.025,
  "taker_fee": 0,
  "royalty_fee": 0.025,
  "data": "[{\"description\":\"This is an example #1\",\"name\":\"NFT Craft 333333333\",\"attributes\":[{\"trait_type\":\"color\",\"value\":\"red\"},{\"trait_type\":\"reveal\",\"value\":\"1654677698\"}],\"image\":\"https://ipfs.io/ipfs/QmVsy5Uq8CuA7GPoyJFpsNQoDiC1csdJVEJU7SoveUAbzg\",\"animation_url\":\"\",\"background_color\":\"\",\"youtube_url\":\"\",\"external_url\":\"\"}]"
}
```

## Marketplace | order-open

- Required Auth Token

`POST`
```
https://api.pinetree.space/marketplace/order/open
```

Request Json Body
```json
{
    "project": "NFT Craft",
    "token_id": 468,
    "payment_token_symbol": "gen",
    "order_price": 150
}
```

Success 200
```json
{
    "message": "success",
    "order_id": 53
}
```

## Marketplace | order-cancel

- Required Auth Token

`POST`
```
https://api.pinetree.space/marketplace/order/cancel
```

Request Json Body
```json
{
    "project": "NFT Craft",
    "token_id": 468
}
```

Success 200
```json
{
    "message": "success",
    "order_id": 53
}
```

## Marketplace | buy

- Required Auth Token

`POST`
```
https://api.pinetree.space/marketplace/order/:orderId/buy
```

Success 200
```json
{
	"message": "success",
	"buyer_account": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
	"order_id": 13,
	"payment_token_symbol": "eth",
	"order_price": 0.2,
	"project_owner": null,
	"royalty_fee": 0.025,
	"nft_owner": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D",
	"hmac": "2ea2d87bf6ee240636742aab024dac99da21f8b6b75dd551752c9366155c2472"
}
```

