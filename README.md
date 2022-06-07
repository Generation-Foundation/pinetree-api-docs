# Pinetree API

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
https://api.pinetree.space/:user/nonce
```

Success 200
```json
{
    "nonce": "2cf05d94db"
}
```

## User | signature (Authentication)

`POST`
```
https://api.pinetree.space/:user/signature
```

Success 200
```json
{
    "user": "0xfd18178e6a2bd20c3943f26f7aa03628003b5c84",
    "token": "exJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0eXBlIjoidXNlciIsImFjY291bnQiOiJiZW5AYmFvYmFicGFydG5lcnMuaW8iLCJpYXQiOjE2NTQxNTg4MTMsImV4cOI6MTY1NDI0NTIxMywiaXNzIjoiQmFvYmFiIFBhcnRuZXJzIn0.F5rAb_JGhDiq5z8ZnpDMw9Gtf8V_-DsrTqM8j5La7AB"
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
    "token-address": "0x179b734d0291fa9e3a4728c7c27866ee25ccc3e0",
    "symbol": "GEN",
    "decimal": 18,
    "balance": 31124359812577
}
```

## Wallet | Internal token send

`POST`
```
https://api.pinetree.space/wallet/token/:tokenAddress/internal-token-send
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