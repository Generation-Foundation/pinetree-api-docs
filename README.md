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
    "nonce": "0xaDef029F4f8BE4F2d03F1f758E95D76F8DF48e1D_1655271907339"
}
```

## User | signature (Authentication)

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

| Field | Type | Description |
|-------|------|----------------|
| tokenAddress | string | ERC20 contract address. If you input 'ethereum', it will return ETH balance. |

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
	"balance": "31124359812577"
}
```

## ~~Wallet | Internal token send~~

`POST`
```
https://api.pinetree.space/wallet/token/:tokenAddress/internalTokenSend
```

Request Json Body
```json
{
    "from": "0xfd18178e6a2bd20c3943f26f7aa03628003b5c84",
    "to": "0xedec843ee5ecdbf54ae7f25cf466d944375860e4",
    "amount": 7261351355566
}
```

Success 200
```json
{
    "message": "success"
}
```

## Project | create

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
    "owner": "0xedec843ee5ecdbf54ae7f25cf466d944375860e4",
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
    "nft_total": 0
}
```

## NFT | mint

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
            "order_id": 52,
            "payment_token_symbol": "gen",
            "maker": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
            "taker": null,
            "submited_at": 1654752367,
            "order_price": 742352000000000000000000,
            "maker_fee": 0.025,
            "taker_fee": 0,
            "detail": {
                "project": "NFT Craft",
                "nft_owner": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
                "token_id": 467,
                "on_sale": true,
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
    "order_id": 52,
    "payment_token_symbol": "gen",
    "maker": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
    "taker": null,
    "submited_at": 1654752367,
    "order_price": 742352000000000000000000,
    "maker_fee": 0.025,
    "taker_fee": 0,
    "detail": {
        "project": "NFT Craft",
        "nft_owner": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
        "token_id": 467,
        "on_sale": true,
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
}
```

## Marketplace | order-open

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
    "order_price": 1500000000000000000
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

`POST`
```
https://api.pinetree.space/marketplace/order/:orderId/buy
```

Success 200
```json
{
    "message": "success",
    "order_id": 53,
    "escrow_id": 24,
    "escrow_address": "0x97e99c73ddf2778dcc8b7b4e8cec8937a46314a8"
}
```

