
# Blockchain-Based EHR Framework

##  Note: This is the last step come to it after following all the steps given above else the application will run in some other port.

## Overview
This framework aims to leverage **blockchain technology** for **Electronic Health Records (EHR)** with a focus on **secure storage and granular access control**. Additionally, it addresses the **scalability issue** commonly faced by blockchain systems by implementing **off-chain storage**. The framework provides a **scalable, secure, and integral blockchain-based EHR solution**.

## Features
- **Blockchain-based EHR storage**
- **Granular access control for users**
- **Off-chain storage for scalability**
- **Secure and decentralized data management**

---

## Installation
This project requires **Node.js** and **npm**. Follow the steps below to set up your development environment.

### 1. Install Node Modules
```sh
cd\your_project_directory\doctor-diagnosis_blockchain\app
npm install
```

### 2. Install Ganache
- Download **Ganache** from [here](https://trufflesuite.com/ganache/).
- If using Linux, you will receive an `.appimage` file. Follow [this guide](https://trufflesuite.com/docs/ganache/quickstart) for installation.

### 3. Install IPFS
- Download **IPFS Desktop** from [GitHub](https://github.com/ipfs/ipfs-desktop/releases).

### 4. Install Local Server (lite-server)
```sh
npm install -g lite-server
```

### 5. Install Metamask
Metamask is a browser extension available for **Chrome, Firefox, and Brave**.
- Install it from [here](https://metamask.io/download/).

---

## Getting the dApp Running

### 1. Configure Ganache
- Open **Ganache** → Click on **Settings** (Top Right Corner).
- Under the **Server** tab:
  - **Hostname**: `127.0.0.1`
  - **Port Number**: `8545`
  - **Enable Automine**
- Under **Accounts & Keys** tab:
  - **Enable Autogenerate HD Mnemonic**

### 2. Configure IPFS
Run the following commands:
```sh
ipfs init
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Origin "[\"*\"]"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Credentials "[\"true\"]"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Methods "[\"PUT\", \"POST\", \"GET\"]"
```
**Note:** If using Windows, run these commands in **Command Prompt** or **Git Bash**.

### 3. Set Up Metamask
- Click the **Metamask** icon in your browser.
- Click **TRY IT NOW** (if prompted for an update).
- Click **Continue**, accept the **Terms & Conditions**.
- **Stop when Metamask asks for a new password**. (We will configure this after deploying the contract.)

---

## Deploying the Smart Contract
### 1. Install Truffle (in app directory)
```sh
npm install -g truffle
```

### 2. Compile Smart Contracts
```sh
truffle compile
```

### 3. Start Local Development Blockchain
- **Open Ganache** and ensure it's configured correctly.
- Open a new **terminal** and deploy contracts:
```sh
truffle migrate
```
- Copy the deployed contract address and update it in `src/app.js`:
  ![image](https://github.com/user-attachments/assets/581b3857-283c-4c14-8ae1-fab0776822da)

```js
// app/src/app.js (Line 11)
var agentContractAddress = '0x75E115394aacC7c6063E593B9292CB9417E4cbeC';
```
- If you change contract contents, **reset deployment**:
```sh
truffle migrate --reset
```
**Note:** Resetting will change the contract address, so update `src/app.js` accordingly.

---

## Running the dApp

### 1. Connect Metamask to Local Blockchain
- **Set network to localhost:8545**.
- Click on right top menu.
<img src="https://github.com/user-attachments/assets/9efd94b3-85d2-4097-a387-0c416936c198" width="300">

- Click on add a network then enter following info given below.

<img src="https://github.com/user-attachments/assets/d301daae-83e3-479d-a283-fab8a813accb" width="300">

- Click **Save**
- Click **Import Account**.
- Copy a **private key** from **Ganache** and import it into **Metamask**.

### 2. Start IPFS
- Open **IPFS Desktop Application**.

### 3. Start the Local Server
```sh
cd /YOUR_PROJECT_DIRECTORY/app/
npm start
```
- Open **`localhost:3001`** in your browser.

That's it! 🎉 Your **dApp** is now running locally. 🚀

