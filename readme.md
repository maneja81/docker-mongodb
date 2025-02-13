# 🚀 MongoDB & Mongo Express - Docker Compose Setup

This repository provides an easy-to-use **Docker Compose setup** for running **MongoDB** with **Mongo Express**. The setup allows you to spin up a **MongoDB database** along with a **web-based UI** for easy database management. Configuration values are loaded dynamically from a `.env` file for flexibility.

---

## 📜 **Table of Contents**
- [🚀 MongoDB \& Mongo Express - Docker Compose Setup](#-mongodb--mongo-express---docker-compose-setup)
  - [📜 **Table of Contents**](#-table-of-contents)
  - [🚀 **Features**](#-features)
  - [📦 **Prerequisites**](#-prerequisites)
  - [📥 **Installation \& Usage**](#-installation--usage)
    - [🔹 **Step 1: Clone the Repository**](#-step-1-clone-the-repository)
    - [🔹 **Step 2: Create a `.env` File**](#-step-2-create-a-env-file)
    - [🔹 **Step 3: Start the Containers**](#-step-3-start-the-containers)
    - [🔹 **Step 4: Verify Running Containers**](#-step-4-verify-running-containers)
  - [⚙️ **Configuration**](#️-configuration)
  - [🛠 **Available Commands**](#-available-commands)
  - [🌐 **Accessing the Services**](#-accessing-the-services)
  - [📄 **Environment Variables**](#-environment-variables)
  - [📂 **Directory Structure**](#-directory-structure)
  - [🛠 **Troubleshooting**](#-troubleshooting)
    - [1️⃣ **MongoDB Connection Issues?**](#1️⃣-mongodb-connection-issues)
    - [2️⃣ **Mongo Express Not Accessible?**](#2️⃣-mongo-express-not-accessible)
    - [3️⃣ **Want to Stop Everything?**](#3️⃣-want-to-stop-everything)
  - [📜 **License**](#-license)
    - [🎯 **Contributing**](#-contributing)

---

## 🚀 **Features**
✅ **Runs MongoDB & Mongo Express** in isolated containers  
✅ **Fully configurable** using an `.env` file  
✅ **Data persistence** using Docker volumes  
✅ **Secure access** with username & password authentication  
✅ **Minimal setup required** - just `docker-compose up -d`  

---

## 📦 **Prerequisites**
Before using this setup, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started) (version 20.x or later)
- [Docker Compose](https://docs.docker.com/compose/install/) (included with Docker Desktop)
- Basic knowledge of Docker and MongoDB (helpful but not required)

---

## 📥 **Installation & Usage**

### 🔹 **Step 1: Clone the Repository**
```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
```

### 🔹 **Step 2: Create a `.env` File**
Copy the provided `.env.example` file and rename it to `.env`:

```sh
cp .env.example .env
```

Modify the `.env` file with your preferred configuration.

### 🔹 **Step 3: Start the Containers**
Run the following command to pull the required images and start the services:

```sh
docker-compose up -d
```

### 🔹 **Step 4: Verify Running Containers**
Check if the MongoDB and Mongo Express services are running:

```sh
docker ps
```

---

## ⚙️ **Configuration**
The setup uses an `.env` file to configure all parameters dynamically.  
Ensure your `.env` file contains correct values before running the containers.

---

## 🛠 **Available Commands**
| Command | Description |
|---------|------------|
| `docker-compose up -d` | Starts the MongoDB & Mongo Express containers in the background |
| `docker-compose down` | Stops and removes all running containers |
| `docker ps` | Lists all running containers |
| `docker-compose logs` | Displays logs for troubleshooting |
| `docker-compose exec mongodb bash` | Opens a shell inside the MongoDB container |

You can also use npm to run these commands and these are configured as follows:
```sh
npm run docker:up
npm run docker:down
npm run docker:list
npm run docker:logs
npm run docker:bash
```
---

## 🌐 **Accessing the Services**
Once the containers are running, access the services via:

- **MongoDB**: Connect using MongoDB Compass or any MongoDB client at:  
  `mongodb://admin:secret@localhost:27017/`  
  _(Replace credentials as per your `.env` file)_

- **Mongo Express**: Open a browser and go to:  
  👉 [http://localhost:8081](http://localhost:8081)  
  _(Login with the username & password from your `.env` file)_

---

## 📄 **Environment Variables**
The `.env` file is used to configure MongoDB and Mongo Express. Below are the available environment variables:

| Variable | Default Value | Description |
|----------|--------------|-------------|
| `MONGO_INITDB_ROOT_USERNAME` | `admin` | Root username for MongoDB |
| `MONGO_INITDB_ROOT_PASSWORD` | `secret` | Root password for MongoDB |
| `MONGO_PORT` | `27017` | Exposed MongoDB port |
| `ME_CONFIG_BASICAUTH_USERNAME` | `admin` | Username for Mongo Express UI |
| `ME_CONFIG_BASICAUTH_PASSWORD` | `secret` | Password for Mongo Express UI |
| `ME_CONFIG_MONGODB_SERVER` | `mongodb` | MongoDB container name |
| `MONGO_EXPRESS_PORT` | `8081` | Port for Mongo Express UI |

👉 _Edit the `.env` file to customize these values._

---

## 📂 **Directory Structure**
```sh
📂 your-repository-name
 ├── 📄 .env.example         # Example environment variables file
 ├── 📄 .env                 # Your custom environment variables (ignored in Git)
 ├── 📄 docker-compose.yml   # Docker Compose configuration file
 ├── 📜 README.md            # Documentation
 └── 📁 volumes              # Docker volume for MongoDB data persistence
```

---

## 🛠 **Troubleshooting**
### 1️⃣ **MongoDB Connection Issues?**
- Ensure MongoDB is running:  
  ```sh
  docker ps
  ```
- Check MongoDB logs:  
  ```sh
  docker-compose logs mongodb
  ```

### 2️⃣ **Mongo Express Not Accessible?**
- Ensure Mongo Express is running:  
  ```sh
  docker ps
  ```
- Try restarting the container:
  ```sh
  docker-compose restart mongo-express
  ```

### 3️⃣ **Want to Stop Everything?**
- Run:
  ```sh
  docker-compose down
  ```

---

## 📜 **License**
This project is licensed under the **MIT License**. You are free to use, modify, and distribute it.

---

### 🎯 **Contributing**
Feel free to fork this repository and submit a pull request with improvements!

📩 **For any issues, raise a GitHub issue or contact me.** 🚀
