# Explorer Link Generator

## Installation

`npm install '@athene-ecosystem/scan-link' -S`
`yarn add '@athene-ecosystem/scan-link'`

## Usage

```javascript
const explorerLink = require("@athene-ecosystem/scan-link");
const networkId = "1";
const chainId = "0x1";
const account = "0x3859b1CE89f368ba936bACafF7DdF62D7E65cE19";
const accountLink = explorerLink.createAccountLink(account, networkId);
const accountLinkForChain = explorerLink.createAccountLinkForChain(
  account,
  chainId
);

const hash =
  "0x44dc0639b26500d3bf63fd01c9106c13f3cab5051e24fd39b3878437b774970a";
const txLink = explorerLink.createExplorerLink(hash, networkId);
const txtLinkForChain = explorerLink.createExplorerLinkForChain(hash, chainId);

const token = "0xdac17f958d2ee523a2206206994597c13d831ec7";
const tokenTrackerLink = explorerLink.createTokenTrackerLink(token, networkId);
// You can also track token balances by account
const accountTokenTrackerLink = explorerLink.createTokenTrackerLink(
  token,
  networkId,
  account
);

const accountTokenTrackerLinkForChain =
  explorerLink.createTokenTrackerLinkForChain(token, chainId, account);

// Create urls for interacting with custom networks
const customNetworkUrl = "https://customnetwork.com/";

const customtTokenTrackerLink = explorerLink.createCustomTokenTrackerLink(
  token,
  customNetworkUrl
);

const customAccountLink = explorerLink.createCustomAccountLink(
  account,
  customNetworkUrl
);

const customExplorerLink = explorerLink.createCustomExplorerLink(
  hash,
  customNetworkUrl
);

// Generate custom or native athene explorer link based on rcpPrefs
const atheneExplorerLink = explorerLink.getatheneExplorerLink(
  transaction,
  rcpPrefs
);

// Generate account link for custom or native network
const getAccountLink = explorerLink.getAccountLink(
  address,
  chainId,
  rpcPrefs,
  networkId
);

// Generate token tracker link for custom or native network
const tokenTrackerLink = explorerLink.getTokenTrackerLink(
  tokenAddress,
  chainId,
  networkId,
  holderAddress,
  rpcPrefs
);
```

## Running tests

```bash
yarn test
```
