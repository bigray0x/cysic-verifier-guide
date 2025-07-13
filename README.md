# cysic-verifier-guide

![Image 6-14-25 at 8 11 AM](https://github.com/user-attachments/assets/355d22c4-3a7b-4155-b897-978332d76034)

Cysic is zero-knowledge (ZK) hardware startup aims to provide hardware acceleration solutions for ZK proof protocols. Cysic team developed a FPGA prototype of multi-scalar multiplication (MSM), which is an important component within ZK protocols.

-> we can contribute to cysic testnet by running a prover or verifier node.

- Verifier - Most minimal requirement.
- Validator - Minimal requirements [although its permissioned].
- Prover - Highest requirement.

### Verifier Requirements :

- Mimimum Of ```8GB``` RAM
- 4 ```Cores``` CPU
- 200GB Storage
- Linux PC Or VPS && MacOS supported.
- Kelpr and any EVM wallet (zerion or metamask recommended)

-> before you start create an evm wallet and export the private key to kelpr to get your evm cosmos type address.

### How to join the testnet

- head to the testnet site [cysic.xyz](https://cysic.xyz/zk/verifier)

 ![image](https://github.com/user-attachments/assets/ccb7221c-4ce8-45b6-9424-b06d7d131ca4)

- connect the EVM wallet and input code ```144dc``` tto get access.

![image](https://github.com/user-attachments/assets/d46effaa-803c-431e-a92b-97eaf01d950d)

- create account with your username.
- connect the kelpr wallet.
- you can connect twitter, discord and email to your profile.
- copy your ```EVM address``` and save it somewhere.

## Verifier Node Setup Guide

### Step 1: Update system and install dependencies :

- Linux OS
```
sudo apt update && sudo apt upgrade -y && sudo apt install -y screen wget
```
- Mac OS
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && brew update && brew install screen wget
```
- Test Functionality
```
screen --version
wget --version
```
### Step 2: Install The Verifier Node :

- replace ```0x-Fill-in-your-reward-address-here``` with your actual with your actual ```EVM address```

```
curl -L https://github.com/cysic-labs/cysic-phase3/releases/download/v1.0.0/setup_linux.sh > ~/setup_linux.sh && bash ~/setup_linux.sh 0x-Fill-in-your-reward-address-here

cd ~/cysic-verifier/ && bash start.sh
```

### This script will do the following job:

- Download the verifier program and library: ```verifier``` & ```libdarwin_verifier.so``` & ```libdarwin_verifier``` & ```librsp.so```

- Create the verifier config file named ```config.toml```

- Create script to run the verifier start.sh

- You can go to ```~/cysic-verifier``` folder to see all the above contents created successfully after running the script.

- Confirm installation :
```
cd  ~/cysic-verifier  && ls -la
```
![image](https://github.com/user-attachments/assets/9637f39d-2b01-40ac-8619-8e74b7a70882)

- if all the files above exists you can proceed.

### Step 3: Start The Verifier Node :

- Create a screen session:

```
screen -S cysic
```

- Start the node

```
cd $HOME && cd ~/cysic-verifier/ && bash start.sh
```
![image](https://github.com/user-attachments/assets/88c9feb0-6a99-49ea-9cc0-6c53c11f662c)
- when the node starts you may get error logs.
- it'll take sometime to properly synchronise so give it time.
- The verifier may need some minutes to connect to the chain. When you see output like ```send heartbeat to server```, then the verifier is running successfully.
- The verifier program will create mnemonic files for you. Your submitted address mnemonic file is in: ```~/.cysic/keys/``` folder, please keep it or you can not run the verifier program again.

