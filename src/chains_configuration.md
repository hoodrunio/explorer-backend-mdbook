# Chains Configuration

Chains configuration is at [`Chains.yml`](https://github.com/testnetrunn/explorer-backend/blob/main/Chains.yml) file.

Rules:

- Every chain definition should start with the `name` key.
- The required keys are `name`, `logo`, `rpc`, `rest`, and `wss`.
- Other keys are either optional or will be generated at compilation.

```yml
name: axelar
logo: https://assets.coingecko.com/coins/images/24489/large/tsYr25vB_400x400.jpg
rpc: https://rpc.cosmos.directory/axelar
rest: https://axelar-api.polkachu.com
wss: wss://axelar-rpc.chainode.tech/websocket
```

## Keys

`name`: The name of the chain. Only use lowercase letters.

`logo`: The URL of the logo of the chain.

`rpc`: The URL of the RPC node of the chain.

`rest`: The URL of the REST API node of the chain.

`wss`: The URL of the Web Socket node of the chain.

`jsonrpc`: The URL of the JSON RPC node of the chain. It is optional.

`epoch`: Is the chain epoch-based? `true` or `false`.

`gecko`: The CoinGecko ID of the chain.

`prefix`: The prefix of the chain. For example, `"osmo"` for Osmosis.

`decimals`: The decimals of the native coin of the chain. Default value is 6.

`version`: The Cosmos SDK version of the chain. It can be generated automatically.

`denom`: The denom of the native coin of the chain. It can be generated automatically.
