## Setup
1. Clone this repository
2. Run `git submodule update --init`

Everytime you need to test a change in prysm or geth, run `git submodule update --remote`

## Running the Devnet
1. (_Optional_) Run `make devnet-clean` to start from a clean slate
2. Run `make devnet-up`
3. Visit http://127.0.0.1:16686 to visualize beacon and validator node traces

## Modify prysm mannet config chainId
```
--- a/config/params/mainnet_config.go
+++ b/config/params/mainnet_config.go
@@ -122,8 +122,8 @@ var mainnetBeaconConfig = &BeaconChainConfig{
        IntervalsPerSlot:   3,
 
        // Ethereum PoW parameters.
-       DepositChainID:         1, // Chain ID of eth1 mainnet.
-       DepositNetworkID:       1, // Network ID of eth1 mainnet.
+       DepositChainID:         9999, // Chain ID of eth1 mainnet.
+       DepositNetworkID:       1,    // Network ID of eth1 mainnet.
        DepositContractAddress: "0x00000000219ab540356cBB839Cbe05303d7705Fa",
 
        // Validator params.

```