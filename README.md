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
- 📖 Reading motivational content.
- 🎨 Drawing for self-expression.
- 🎵 Listening to calming music.

### 4. Contact Therapist Simulation
- A **simulated one-on-one therapy session**.
- Includes a basic **sign language to text conversion model**.
- Currently supports simple gestures like:
  - ✋ Showing all five fingers = **"Hello"**
  - ✊ Making a fist towards the camera = **"No"**

### 5. Virtual Environment for Awareness
- An interactive **3D space** designed to increase engagement and awareness about mental health.

### 6. Dynamic Mode (3D Interactive Experience)
- A **3D-controlled character** navigates teleport points on the map to **access different features of the platform** interactively.

### 7. Secure Patient Diagnosis & Blockchain Storage
- **Patient records** are stored securely with **encryption**.
- Only **hash values** are stored on the **blockchain** to ensure privacy and security while maintaining public accessibility.

---

## Setup Instructions

To run **Aura+**, follow these steps:

### **1. Dashboard with Authentication & Therapy Cards**
```sh
cd DashboardWithAuthAndTherapyCards/client
npm i 
npm run dev

cd DashboardWithAuthAndTherapyCards/server
npm i 
npm start

### **2. Dynamic Mode (3D Interactive Aura)**
```sh

cd Dynamic-Aura
npm i 
set PORT=6003
npm start

### **3. Face Authentication System**
```sh

cd FaceAuthForDisabled
npm i 
npm run dev

### **4. AI Mental Health Chatbot**
```sh

cd MentalHealthChatBot/client
npm i 
set PORT=6001
npm start

cd MentalHealthChatBot/server
npm i 
npm start

### **5. Therapist Video Call for Disabled Users**
```sh

cd TherapistVideoCallforDisabled
npm i 
set PORT=6002
npm start 


