# Blockchain Configuration

This directory contains configuration files for blockchain connectivity.

## blockchain.json

This file contains the network and contract configurations for the NFT metadata viewer.

### Structure

```json
{
  "networks": {
    "bonsoleil": {
      "name": "Network display name",
      "rpcUrl": "RPC endpoint URL",
      "chainId": 21201,
      "contracts": {
        "metadataBank": {
          "address": "Contract address",
          "abi": ["Contract ABI"]
        }
      }
    }
  },
  "defaultNetwork": "bonsoleil"
}
```

### Current Configuration

- **Network**: Bon-Soleil Testnet
- **RPC URL**: https://dev2.bon-soleil.com/rpc
- **MetadataBank Contract**: 0x5143f16dA9bE850da6c11cB50A7359A36e1D349b

### Usage

The configuration is automatically loaded by `generate.html` when the page loads. If the configuration file cannot be loaded, the system will fall back to hardcoded default values.

### Adding New Networks

To add a new network, add a new entry under the `networks` object:

```json
"networks": {
  "bonsoleil": { ... },
  "newnetwork": {
    "name": "New Network",
    "rpcUrl": "https://new-rpc-url.com",
    "contracts": {
      "metadataBank": {
        "address": "0x...",
        "abi": [...]
      }
    }
  }
}
```

Then update `defaultNetwork` to use the new network:

```json
"defaultNetwork": "newnetwork"
```
