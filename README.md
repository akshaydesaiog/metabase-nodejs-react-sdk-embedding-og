Here's the formatted content for a `README.md` file:

```markdown
# Metabase Embedding SDK for React Sample Application

This repository contains a sample application demonstrating the use of the Metabase Embedding SDK with React. 
You can choose to set up the application using Docker or manually for local development.


> **Note:**  
> This SDK is compatible with Metabase v1.50 or higher. You'll need a Pro or Enterprise version of Metabase up and running. 
> If you're not sure where to start, sign up for [Pro Cloud](https://www.metabase.com/pricing).
```
---

## Quick Start with Docker

If you prefer a containerized environment, follow these steps:

### Prerequisites

- Install [Docker](https://docs.docker.com/get-docker/) on your system.

---
### Steps

1. **Clone the repository:**
   ```bash
   gh repo clone akshaydesaiog/metabase-nodejs-react-sdk-embedding-og
   cd metabase-nodejs-react-sdk-embedding-og
   ```

2. **Copy the environment file:**
   ```bash
   cp .env.example client/.env
   cp .env.example server/.env
   ```

3. **Adjust URLs in `.env`:**
   - Set `VITE_METABASE_INSTANCE_URL` and `METABASE_INSTANCE_URL` to point to your Metabase instance (e.g., `http://localhost:3000`).
   - Set `VITE_AUTH_PROVIDER_URI` (e.g., `http://localhost:9090/sso/metabase`).
   - Set the `METABASE_JWT_SHARED_SECRET` from your Metabase Admin Panel.

4. **Build and run the application using Docker Compose:**
   ```bash
   cd server
   docker build -t metabase-embedding-server .
   docker run -d -p 9090:9090 --name metabase-embedding-server metabase-embedding-server

   cd ../client
   docker build -t metabase-embedding-client .
   docker run -d -p 3100:3100 --name metabase-embedding-client metabase-embedding-client
   ```

5. **Access the application:**
   - Server runs on: [http://localhost:9090](http://localhost:9090)
   - Client runs on: [http://localhost:3100](http://localhost:3100)

---

## Manual Setup for Local Development

If you prefer to run the application locally without Docker, follow these steps:

### Prerequisites

- Install [Node.js](https://nodejs.org/) (v18 or higher recommended).

### Steps

#### 1. Set up the server

1. **Change to the `server` directory:**
   ```bash
   cd server
   ```

2. **Install server dependencies:**
   ```bash
   npm install
   ```

3. **Start the server:**
   ```bash
   npm start
   ```

#### 2. Set up the client

1. **Open a new terminal and change to the `client` directory:**
   ```bash
   cd client
   ```

2. **Install client dependencies:**
   ```bash
   npm install
   ```

3. **Start the client application:**
   ```bash
   npm start
   ```

4. **Access the client:**  
   The app runs on [http://localhost:3100](http://localhost:3100).

---

## Configure Metabase for JWT Authentication

To use JWT authentication with Metabase:

1. **Enable SSO with JWT in Metabase:**
   - Navigate to **Admin Settings** > **Authentication** > **JWT**.
   - Click **Setup** and configure the **JWT IDENTITY PROVIDER URI** (e.g., `http://localhost:9090/sso/metabase`).

2. **Generate the JWT signing key:**
   - Copy the generated key into your `.env` file under `METABASE_JWT_SHARED_SECRET`.

---

## Additional Configuration

### Setting up Groups and Data Sandboxing

To enable interactive embedding and data sandboxing, follow the [quick start guide](https://www.metabase.com/learn/customer-facing-analytics/interactive-embedding-quick-start).

---

## Reporting Issues

Please report bugs or feature requests as issues in this repository. For security vulnerabilities, refer to our [Security Policy](https://github.com/metabase/metabase/security#reporting-a-vulnerability).

---

## License

This project is licensed under the MIT license. See the [LICENSE](./LICENSE) file for more information.