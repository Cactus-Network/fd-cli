Credit to the Flora-Network team for creating and sharing this coin recovery script. The contents below are unique to the Cactus Blockchain Network (Ports, Paths, Windows Install Instructions, etc)<p>
#Example Command: fd-cli nft-recover -l "$LAUNCHER_HASH" -p "$POOL_CONTRACT_ADDRESS" -nh 127.0.0.1 -np 11555 -ct C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.crt -ck C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.key   <p>
#Cactus Full Node Port is 11555

<p>
# Install (Linux Users; Scroll down for Windows Users)

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

```
# WINDOWS USERS:
```shell
Recover 7/8 NFT Plot Rewards for the Cactus Blockchain
Install these Requirements: 
Python: https://www.python.org/downloads/ 
Git: https://git-scm.com/downloads 
Then open Windows PowerShell ISE (type Powershell in the search bar and click the app) 
Then type the commands below (update the paths for the two $Env variables)
  
$Env:FD_CLI_BC_DB_PATH = "C:/Users/YourUserName/.cactus/mainnet/db/blockchain_v1_mainnet.sqlite"
$Env:FD_CLI_WT_DB_PATH = "C:/Users/YourUserName/.cactus/mainnet/wallet/db/blockchain_wallet_v1_mainnet_<fingerprint>.sqlite"

git clone https://github.com/Cactus-Network/fd-cli 
cd fd-cli 
python -m venv venv 
.\venv\Scripts\activate 
pip install -e . --extra-index-url https://pypi.chia.net/simple/ 
  
#Test your setup by running:
fd-cli nft-recover --help 
You should see a an ouput with Usage and Options 

#Then run commands below to recover your Rewards ($LAUNCHER_HASH and $POOL_CONTRACT_ADDRESS can be set as environmental variables, or you can type 'text' into the fd-cli command)
 Example: fd-cli nft-recover -l $LAUNCHER_HASH -p $POOL_CONTRACT_ADDRESS -nh 127.0.0.1 -np 11555 -ct C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.crt -ck C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.key   

fd-cli nft-recover 
  -l "$LAUNCHER_HASH" (or just copy/paste your Launcher Hash between the quotes)
  -p "$POOL_CONTRACT_ADDRESS" (or just copy/paste your Pool contract address between the quotes)
  -nh 127.0.0.1 
  -np 11555
  -ct C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.crt 
  -ck C:/Users/YourUserName/.cactus/mainnet/config/ssl/full_node/private_full_node.key
  
# All coins that were mined +7 days ago WITH NFT PLOT should be spendable soon via wallet.
  
#Setting environment variable paths in Windows PowerShell:

# Set env var to blockchain path.
$Env:FD_CLI_BC_DB_PATH = "C:/Users/YourUserName/.cactus/mainnet/db/blockchain_v1_mainnet.sqlite"

# Set env var to wallet path.
# This must be wallet that is associated with mnemonic from which NFT plot was created.
$Env:FD_CLI_WT_DB_PATH = "C:/Users/YourUserName/.cactus/mainnet/wallet/db/blockchain_wallet_v1_mainnet_<fingerprint>.sqlite"

# Set env var to launcher id of NFT plot.
$Env:LAUNCHER_HASH="yourLauncherHash"
#(Linux Users) export LAUNCHER_HASH=aaa0cbae497933a6c029a3819759fe148829dfde0316cb0512ccad23edce6aaa

# Set env var to pool_contract_address. 
$Env:POOL_CONTRACT_ADDRESS="yourPoolContractAddress" #Scroll down to see how to find this
#(Linux Users) export POOL_CONTRACT_ADDRESS=xch13rht0xz4tpdqfq08e3dk20kewg9cjj3pw0wwjf7vay8whlxn7ppqapeqhz
```
Address -> Puzzle Hash:
https://www.chiaexplorer.com/tools/address-puzzlehash-converter 
```
