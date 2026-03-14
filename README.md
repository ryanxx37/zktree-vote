# zktree-vote
Anonymous voting on Ethereum blockchain using zero knowledge proof

## Usage

- Clone the repository by `git clone https://github.com/ryanxx37/zktree-vote`
- Install wget (by `apt-get install wget` on Ubuntu/Debian)
- Install the project dependencies and prepare by `npm install` in the project directory
- Start a Hardhat node by `npx hardhat node` in the project directory
- In another terminal deploy the smartcontract by `npm run deploy`
- Start the app by `npm start`

The app uses MetaMask to connect the blockchain, so the MetaMask extension have to be installed, and connected to the Hardhat local node. The smart contract owner is the first Hardhat account, and the second account is set as a validator by the deployment script.

For more details, please read my article on [Medium](https://thebojda.medium.com/how-i-built-an-anonymous-voting-system-on-the-ethereum-blockchain-using-zero-knowledge-proof-d5ab286228fd)


====================================================================================================================================
Building an Anonymous Voting System on the Ethereum Blockchain Using Zero-Knowledge Proofs
This article uses Ubuntu 22.04 as the operating environment.

Preparation
Download the Repository
Download the zktree-vote repository and enter the directory:

Bash
git clone https://github.com/TheBojda/zktree-vote
cd zktree-vote
Install MetaMask
MetaMask is a wallet tool for Ethereum. Install the MetaMask extension for your browser (Firefox or Chrome). This guide uses Chrome.

Install npm
Execute the command sudo apt install npm and enter y when prompted.

Install Environment via npm
The package.json file in the project directory defines the necessary packages. Run npm i to automatically download these into the current directory. You may see a notice regarding 2 high severity vulnerabilities; these can be ignored.

If you attempt to run npm run deploy at this stage, a syntax error will occur because the default node version is too low (e.g., v12.22.9). You must install nvm and use it to install Node.js version 18.

Upgrade Node.js
Follow these steps to upgrade Node.js using nvm:

Bash
sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 
source ~/.bashrc   
nvm install 18
node -v
Confirm the upgrade was successful by checking that node -v outputs a version like v18.18.2.

Deploying the Smart Contract
First, start a local blockchain node by executing:
npx hardhat node

This will start a local testing network and display several Accounts and Private Keys.

Warning: These accounts are for local testing only. Never send real funds to them.

Connect MetaMask to the Local Network
Add the local network (typically http://127.0.0.1:8545/) to MetaMask.

Import the provided private keys into MetaMask to access the test accounts.

Deploy the Contract
Open a second terminal window, navigate to the zktree-vote directory, and run:

Bash
npm run deploy
Upon success, the terminal will display the addresses for the MiMC sponge hasher, the Verifier, and the ZKTreeVote contract.

Accessing the Voting System via Browser
Execute npm start and visit localhost:1234 in your browser:

Generate Commitment: Use the second option in the interface to copy your commitment.

Validate: Use the first option to validate. Ensure the active account in MetaMask is the imported test account (e.g., Account #1).

Vote: Cast your vote. After clicking "Send to blockchain," wait a moment for the MetaMask confirmation window to appear.

Results: View the final voting results.
