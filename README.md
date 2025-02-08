# Aura+ - A Mental Health Platform for Physically Disabled Individuals

## Introduction
**Aura+** is an innovative mental health platform designed specifically for physically disabled individuals. Our project integrates multiple technologies to provide a seamless and accessible mental health support system. It offers **face authentication login, an AI therapist chatbot, therapy tools, virtual environments, and secure patient record storage using blockchain encryption**.

---

## Features

### 1. Multi-Biometric Authentication (Face Authentication)
- The initial plan was to implement a three-step biometric authentication system using **face recognition, voice authentication, and dynamic text reading**.
- Due to time constraints, only **face authentication** is currently implemented.

### 2. AI Therapist Chatbot
- A chatbot that interacts with users to provide **mental health support**.
- After each conversation, a **log is created and analyzed using NLP**.
- The sentiment of the conversation is visualized on a **dashboard** to indicate signs of **depression, anxiety, and overall mood**.

### 3. Therapy Cards
A dedicated section for **therapeutic activities** such as:
- 📖 Reading motivational content
- 🎨 Drawing for self-expression
- 🎵 Listening to calming music

### 4. Contact Therapist Simulation
- A **simulated one-on-one therapy session**
- Includes a basic **sign language to text conversion model**
- Currently supports simple gestures like:
  - ✋ Showing all five fingers = **"Hello"**
  - ✊ Making a fist towards the camera = **"No"**

### 5. Virtual Environment for Awareness
- An interactive **3D space** designed to increase engagement and awareness about mental health.

### 6. Dynamic Mode (3D Interactive Experience)
- A **3D-controlled character** navigates teleport points on the map to **access different features of the platform** interactively.

### 7. Secure Patient Diagnosis & Blockchain Storage
- **Patient records** are stored securely with **encryption**
- Only **hash values** are stored on the **blockchain** to ensure privacy and security while maintaining public accessibility

---

## Setup Instructions

To run **Aura+**, you'll need to open multiple terminal windows for different components. Follow these steps:

### 1. Dashboard with Authentication & Therapy Cards
**Terminal 1 - Client:**
```sh
cd DashboardWithAuthAndTherapyCards/client
npm i
npm run dev
```

**Terminal 2 - Server:**
```sh
cd DashboardWithAuthAndTherapyCards/server
npm i
npm start
```

### 2. Dynamic Mode (3D Interactive Aura)
**Terminal 3:**
```sh
cd Dynamic-Aura
npm i
set PORT=6003
npm start
```

### 3. Face Authentication System
**Terminal 4:**
```sh
cd FaceAuthForDisabled
npm run dev
```

### 4. AI Mental Health Chatbot
**Terminal 5 - Client:**
```sh
cd MentalHealthChatBot/client
npm i
set PORT=6001
npm start
```

**Terminal 6 - Server:**
```sh
cd MentalHealthChatBot/server
npm i
npm start
```

### 5. Therapist Video Call for Disabled Users
**Terminal 7:**
```sh
cd TherapistVideoCallforDisabled
npm i
set PORT=6002
npm start
```

## Important Notes
* The **sign language recognition model** requires a **well-lit environment**
* The **face authentication system** is currently the only biometric method implemented
* Each component must be run in a separate terminal window to function properly
* Ensure all required ports (6001, 6002, 6003) are available before starting the services

## Future Improvements
* A **more robust sign language model**
* Completion of **multi-biometric authentication**
* Enhanced integration between components
* Expanded therapy tool collection
* Improved virtual environment interactions

## Technologies Used
* Frontend: React.js
* Backend: Node.js
* Authentication: Face Recognition API
* Database: Blockchain Technology
* 3D Environment: Three.js
* Video Calls: WebRTC
* AI Chatbot: Natural Language Processing

## Team & Credits
Developed by **[Your Team Name]** for **[Hackathon Name]**

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Contact
For any queries or support, please reach out to:
* Email: [Your Email]
* GitHub: [Your GitHub Profile]

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

