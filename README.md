# ⚙️How to run a Hemi Miner (Mainnet)⚙️
![image](https://github.com/user-attachments/assets/e3deafee-6310-45a6-b3d9-6d33539a07c4)

---
## Step 1 : Setting up a VPS

You can choose CLOUP VPS 2 on Contabo : https://www.tkqlhce.com/click-101114590-13484397

![image](https://github.com/user-attachments/assets/0848b3d0-8a01-4b50-9adb-5a95d181fa75)

Select Ubuntu 22.04

![image](https://github.com/user-attachments/assets/50143399-91e5-4e71-b7e9-0d46d7462caa)


## Step 2: Connect to your VPS
```
ssh root@<IP_OF_YOUR_VPS>
```
## Step 3: Setup your Hemi node

- Update your system
```
sudo apt update && sudo apt upgrade -y
```
- Install screen
```
sudo apt install screen
```
- Install Hemi file
```
mkdir POP && cd POP && wget https://github.com/hemilabs/heminetwork/releases/download/v1.0.0/heminetwork_v1.0.0_linux_amd64.tar.gz
tar -xvzf heminetwork_v1.0.0_linux_amd64.tar.gz
```
- Create an Hemi Screen
```
screen -S Hemi
```
- Go to Hemi directory
```
cd heminetwork_v1.0.0_linux_amd64
```
- Verify the config of the node
```
./popmd --help
```
- Give permission to wallet file
```
chmod +x keygen && ./keygen -secp256k1 -json -net="mainnet" > ~/popm-address.json
```
- Save your wallet
```
cat ~/popm-address.json
```
- Fund your address with BTC send it to the pubkey_hash
pubkey_hash = wallet address

Set the node gas fees (replace fee_per_vB_integer by the amount for gas fee)
I recommend you to setup to 3

- You can check the current gas fee here => https://mempool.space/
```
export POPM_STATIC_FEE=<fee_per_vB_integer>
```
- Set Mainnet to env variable
```
export POPM_BTC_CHAIN_NAME=mainnet
```
- Launch your node
```
./popmd
```
- Leave your screen CTRL+A+D

---
Thank’s for reading
If you need help you can join Discord : https://discord.com/invite/szXyZSgSYg
Twitter : https://x.com/TRTtheSalad
Disclaimer : Not a financial Advice an education tutorial do your own research
