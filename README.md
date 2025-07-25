# Leaz Starter Website for Zackathon 2025

Welcome to the Zackathon 2025! This guide will help you get the project running in minutes.

---

## 1. Technology Stack

This project is a full-stack application built with a specific set of technologies. The setup is designed to be consistent for all participants using Docker.

| Category      | Technology            | Version              | Notes                                            |
| :------------ | :-------------------- | :------------------- | :----------------------------------------------- |
| **Backend** | Spring Boot           | `2.5.4`              | Java Framework                                   |
|               | Gradle                | `7.0`                | Build Tool (managed by the wrapper)              |
|               | Java (Eclipse Temurin)| `11.0.27`            | Required JDK                                     |
| **Frontend** | Angular               | `17`                 | UI Framework                                     |
|               | Node.js               | `18.13.0` or later   | JavaScript Runtime (v18.20.8 recommended)        |
| **Database** | MySQL                 | `8.0.35`             | Relational Database (managed by Docker)          |
| **Container** | Docker                | -                    | For running the backend and database consistently|

---

## 2. Environment Setup

Before cloning the project, please ensure you have these three tools installed.

1.  **Git:** To clone the repository.
2.  **Docker Desktop:** This is essential. It will run both the backend and the database in isolated containers, ensuring a perfect setup every time. [**Download Docker Desktop here**](https://www.docker.com/products/docker-desktop/).
3.  **NVM (Node Version Manager):** This is the best way to manage Node.js versions.
    * **Windows:** Install from the [**nvm-windows releases page**](https://github.com/coreybutler/nvm-windows/releases).
    * **macOS/Linux:** Install using the script from the [**official NVM repository**](https://github.com/nvm-sh/nvm).

---

## 3. Running the Application

Follow these instructions to get the project running. The entire process uses two separate terminal windows.

### **Terminal 1: Start the Backend & Database**

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/TorinAnderson/Zackathon_2025.git
    cd Zackathon_2025
    ```

2.  **Navigate to the Backend Folder:**
    ```bash
    cd Leaz_backend
    ```

3.  **Update Database Password (Optional):**
    * The project is pre-configured to use `your_strong_password` for the database. If you wish to change it, update the `MYSQL_ROOT_PASSWORD` and `SPRING_DATASOURCE_PASSWORD` values in the `docker-compose.yml` file.

4.  **Start the Backend and Database:**
    * **Important:** Open the Docker Desktop application and make sure it is running.
    * From the `Leaz_backend` folder, run the Docker Compose command:
        ```bash
        docker-compose up --build
        ```
    * The first time you run this, it will take a few minutes to download and build the MySQL and Java images. Subsequent launches will be much faster.

Your entire backend, including the MySQL 8.0.35 database, is now running. The database is accessible on `localhost:3306` through MySQL workbench and the backend API is on `http://localhost:8080`. You can leave this terminal window open.

### **Terminal 2: Start the Frontend**

1.  **Navigate to the Frontend Folder:**
    ```bash
    cd Leaz_frontend
    ```

2.  **Set up the Correct Node.js Version:**
    * Run the following commands to install and use the correct version of Node.js. On Windows, you may need to run this in a terminal with **administrator privileges**.
        ```bash
        nvm install 18.20.8
        nvm use 18.20.8
        ```

3.  **Install Dependencies and Run:**
    * Run the npm install command to download all necessary libraries:
        ```bash
        npm install
        npm install angular-froala-wysiwyg
        ```
    * Start the Angular development server:
        ```bash
        ng serve
        ```

Your frontend application is now running and accessible at **`http://localhost:4200`**. You are ready to start coding!
