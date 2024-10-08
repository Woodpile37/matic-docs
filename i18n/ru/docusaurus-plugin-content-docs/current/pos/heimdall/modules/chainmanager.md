---
id: chainmanager
title: Chain Manager
description: This module provides all necessary dependencies like `contract-addresses`, `bor_chain_id,` and `tx_confirmation_time`. Other parameters can be added to this later on.
keywords:
  - docs
  - matic
image: https://matic.network/banners/matic-network-16x9.png
---

## Overview

This document specifies an overview of the chain manager module of Heimdall

This module provides all necessary dependencies like `contract-addresses`, `bor_chain_id,` and `tx_confirmation_time`. Other parameters can be added to this later on.

Params are updated through the `gov` module.

## Types

Chainmanager structure on Heimdall looks like the following:

```go
type ChainParams struct {
    // BorChainID is valid bor chainId
    BorChainID            string                  `json:"bor_chain_id" yaml:"bor_chain_id"`

    // MaticTokenAddress is valid matic token address
    MaticTokenAddress     hmTypes.HeimdallAddress `json:"matic_token_address" yaml:"matic_token_address"`

    // StakingManagerAddress is valid contract address
    StakingManagerAddress hmTypes.HeimdallAddress `json:"staking_manager_address" yaml:"staking_manager_address"`

    // RootChainAddress is valid contract address
    RootChainAddress      hmTypes.HeimdallAddress `json:"root_chain_address" yaml:"root_chain_address"`

    // StakingInfoAddress is valid contract address
    StakingInfoAddress    hmTypes.HeimdallAddress `json:"staking_info_address" yaml:"staking_info_address"`

    // StateSendedAddress is valid contract address
    StateSenderAddress    hmTypes.HeimdallAddress `json:"state_sender_address" yaml:"state_sender_address"`

    // Bor Chain Contracts
    // StateReceiveAddress is valid contract address
    StateReceiverAddress hmTypes.HeimdallAddress `json:"state_receiver_address" yaml:"state_receiver_address"`

    // ValidatorSetAddress is valid contract address
    ValidatorSetAddress  hmTypes.HeimdallAddress `json:"validator_set_address" yaml:"validator_set_address"`
}
```

## CLI commands

### params

To print all params

```go
heimdallcli query chainmanager params --trust-node
```

### Expected Result

```yaml
tx_confirmation_time: 12s
chain_params:
  bor_chain_id: "15001"
  matic_token_address: "0x0000000000000000000000000000000000000000"
  staking_manager_address: "0x0000000000000000000000000000000000000000"
  root_chain_address: "0x0000000000000000000000000000000000000000"
  staking_info_address: "0x0000000000000000000000000000000000000000"
  state_sender_address: "0x0000000000000000000000000000000000000000"
  state_receiver_address: "0x0000000000000000000000000000000000000000"
  validator_set_address: "0x0000000000000000000000000000000000000000"
```

### REST APIs

| Name   | Method | URL                 |
| ------ | ------ | ------------------- |
| Params | GET    | chainmanager/params |


All query APIs will result in the following format:

```json
{
    "height": "1",
    "result": {
        ...   
    }
}
```