Credit to the Flora-Network team for creating and sharing this coin recovery script.
<p>
# Install

```shell

git clone https://github.com/Cactus-Network/fd-cli.git

python3 -m venv venv
source venv/bin/activate
pip install -e . --extra-index-url https://pypi.chia.net/simple/
```

# NFT 7/8 reward recovery

```shell

# Set env var to blockchain path.
export FD_CLI_BC_DB_PATH=/root/.cactus/mainnet/db/blockchain_v1_mainnet.sqlite
# Set env var to wallet path.
# This must be wallet that is associated with mnemonic from which NFT plot was created.
export FD_CLI_WT_DB_PATH=/root/.cactus/mainnet/wallet/db/blockchain_wallet_v1_mainnet_<fingerprint>.sqlite

# Set env var to launcher id of NFT plot.
export LAUNCHER_HASH=aaa0cbae497933a6c029a3819759fe148829dfde0316cb0512ccad23edce6aaa
# Set env var to pool_contract_address. 
export POOL_CONTRACT_ADDRESS=xch13rht0xz4tpdqfq08e3dk20kewg9cjj3pw0wwjf7vay8whlxn7ppqapeqhz

fd-cli nft-recover \
  -l "$LAUNCHER_HASH" \
  -p "$POOL_CONTRACT_ADDRESS" \
  -nh 127.0.0.1 \
  -np 18755 \
  -ct /root/.cactus/mainnet/config/ssl/full_node/private_full_node.crt \
  -ck /root/.cactus/mainnet/config/ssl/full_node/private_full_node.key
  
# All coins that were mined +7 days ago WITH NFT PLOT should be spendable soon via wallet.

FAQ
How to find CONTRACT_HASH?
cd chia-blockhain
. ./activate
chia plotnft show
Wallet height: 5344
Sync status: Not synced
Wallet id 2: 
Current state: SELF_POOLING
Current state from block height: 1739
Launcher ID: eaf0cbae497933a6c029a3819759fe148829dfde0316cb0512ccad23edce6afa
Target address (not for plotting): xch1tcryankcz0p9ueh9dhyrh0w0zgkdpllpvradwmn5ut2p7peg8k8qhvamzr
Number of plots: 0
Owner public key: 908229fec969abd228336d0ba2ceff6cc4f074bc57e2730a7a960076d3188d6afd8b8068dd1cf40e31268a7e6420b8fa
<b>**Pool contract address (use ONLY for plotting - do not send money to this address): xch13rht0xz4tpdqfq08e3dk20kewg9cjj3pw0wwjf7vay8whlxn7ppqapeqhz**</b>
Claimable balance: 0.0 xch (0 mojo)

Take the Pool contract address and decode it with use of https://www.chiaexplorer.com/tools/address-puzzlehash-converter into puzzle_hash, then you take this puzzle without leading hexadecimal '0x' and that is contract hash you are seeking for.
```

