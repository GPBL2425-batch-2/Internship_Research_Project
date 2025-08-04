# Robot Compost Control Panel Frontend

## 📄 Introduction

This repository contains the frontend application for the robot compost system. It provides a modern, responsive user interface (UI) built with React and TypeScript to monitor and control the compost process. The frontend communicates with a separate Express.js backend for data retrieval and a Python-based Raspberry Pi controller for system management.

This project was developed during an internship for the polytechnic's Computer Engineering program and serves as a foundation for future development by subsequent intern teams.

### ✨ Key Features

- **Dashboard (`MeasureTab`):** Provides a real-time overview of the compost system's status and current phase (e.g., Curing, Mesophilic, Thermophilic).
- **Graphical Visualization (`AngraphTab`):** Displays real-time and historical temperature and humidity data in a clear graph format.
- **Sensor Readings (`SensorReadingsTab`):** A direct view of raw data from the MySQL database, useful for debugging and data analysis.

### 💻 Technologies Used

- **React & TypeScript:** Frontend framework and language for building a robust UI.
- **Vite:** A fast build tool for modern web projects.
- **Express.js Backend:** Communicates with a separate Node.js backend for API calls.
- **AWS Services:** The application is configured to interact with backend services hosted on AWS Lambda, S3, and Route 53.

## 🚀 Getting Started

### 📝 Prerequisites

Before you can run the application, ensure you have the following installed:

- **Node.js**: Version **v22.14.0** or later.
- **npm**: The package manager that comes with Node.js.
- **Git**: For cloning the repository.

### 📦 Installation

Install node, vscode, xampp before working on this. Learn about vs code, github, react typescript and javascript beforehand.
    ```

### ⚙️ Configuration

The frontend's API endpoint is currently hardcoded within the source files. For local development, you must update the URL to point to a local Express.js server.

1.  **Locate the API call:** Find the relevant `fetch` call in the source code. A common location would be within the component files that retrieve data.

2.  **Change the API URL:**
    - The current URL points to the AWS Lambda endpoint:
      `https://cvnhjf6hpj.execute-api.us-east-1.amazonaws.com/getGraphData?`
    - **For local testing**, change this line to point to your local backend server:
      `http://localhost:3000/getGraphData?`

> **Warning:** This hardcoded URL needs to be managed carefully. For deployment, you will need to re-configure this to point to the correct production backend endpoint.

### ▶️ Running the Application

-   **Development Mode:** To run the application in a live-reloading development server:
    ```sh
    npm run dev
    ```
    This will typically open the application in your browser at `http://localhost:5173`.

-   **Production Build:** To create a static production build of the application:
    ```sh
    npm run build
    ```
    The output will be placed in the `dist` folder.

---

### **2. Documentation for `Control_panel_backend` (Express.js)**

This is the `README.md` that would go in your backend repository.

```markdown
# Robot Compost Control Panel Backend

## 📄 Introduction

This repository contains the Express.js backend server for the robot compost system. It is responsible for handling API requests from the frontend, processing data, and managing communication with the Raspberry Pi controller.

### 💻 Technologies Used

- **Express.js & Node.js:** The core framework for building the backend API.
- **MySQL:** A database for storing and retrieving sensor data.
- **AWS Services:** Hosted on AWS Lambda with an API Gateway endpoint.

## 🚀 Getting Started

### 📝 Prerequisites

-   **Node.js**: Version **v22.14.0** or later.
-   **npm**: For package management.
-   **MySQL Database:** An instance of MySQL running locally or remotely.
-   **Raspberry Pi:** A physical Raspberry Pi computer is required for the full system.

### 📦 Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/Marcuswzh/Control_panel_backend.git
    cd Control_panel_backend
    ```

2.  **Install dependencies:**
    ```sh
    npm install
    ```

### ⚙️ Configuration

-   **Environment Variables:** This backend requires sensitive configuration details, such as database credentials and AWS API keys. These were stored in a `.env` file, which is not committed to the repository for security.
-   **Lab-Specific Details:** Crucial information, including **MySQL database credentials, AWS API keys, and MQTT broker details**, are recorded on the physical whiteboard in the lab. The next batch of interns must use this information to set up their `.env` file and configure their AWS services.

### ▶️ Running the Application

1.  **Start the Backend Server:**
    > **<PLACEHOLDER: Please provide the exact command to start the server. This is usually `npm start` or `node server.js`>**.

### 🤖 Raspberry Pi Python Code

> **Important:** The Python code for the Raspberry Pi controller is **not** included in this repository. It is located on the physical Raspberry Pi computer in the lab.

-   **Code Location:** The Python files are stored at the following path on the Raspberry Pi:
    `/home/globalpbl2425/PBL2425/`
-   **Dependencies:** The Python dependencies must be installed in a virtual environment (`.venv`).
-   **Running the Script:** To run the main Python controller script, use the following command:
    ```sh
    /home/globalpbl2425/PBL2425/.venv/bin/python /home/globalpbl2425/PBL2425/__init__v3.py
    ```

---
