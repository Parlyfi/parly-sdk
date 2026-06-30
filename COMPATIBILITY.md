# Compatibility

- `@parly/sdk@16.9.9` is compatible with Parly core `16.9.9`
- compatible with Parly MCP `16.9.9-mcp.0`
- proof model: joinsplit 10-output padded batch
- settlement domain: Tempo `4217`
- asset lanes: USDC.e (`assetId: 1`) and USDT0 (`assetId: 2`)
- MPP sessions are counterparty-locked and spend-limit checked before settlement
- batch send supports 1 to 10 same-chain payout lanes
