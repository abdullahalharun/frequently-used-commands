# Express next.js project dockerize
This repository contains code for express next.js application.

# Deployment Guide
This guide outlines the steps to deploy the project, which includes a frontend built with Next.js, a backend built with Express.js, and MongoDB as the database. The project also uses Cloudinary for storage and Nylas for email services.


## Deployment Instructions using Docker

## Prerequisites

Before you begin, ensure you have the following installed:

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

## Steps for Deployment

### 1. Clone the Project Repository

If you haven't already, clone the project repository:

```bash
git clone https://github.com/your-repository/project.git
cd project
```

### 2. Build and Start the Services

From the root directory of your project, run the following command to build and start all the services defined in `docker-compose.yml`:

```bash
docker compose up --build
```

This will:

- Build the Docker images for both the frontend and backend using the respective Dockerfiles.
- Start the MongoDB service.
- Set up the environment for communication between the frontend, backend, and MongoDB.

### 3. Accessing the Application

Once the containers are up and running, you can access the following:

- **Frontend**: Open your browser and go to `http://localhost:3000` to access the frontend of the project.
- **Backend**: The backend will be available at `http://localhost:5000` (useful for testing API endpoints directly).

### 4. Stopping the Services

To stop the running services, use:

```bash
docker compose down
```

This will stop and remove the containers, networks, and volumes associated with the services.

### 5. (Optional) Running the Application in Detached Mode

If you want to run the services in the background, you can use the `-d` flag:

```bash
docker compose up --build -d
```

This will run the services in detached mode, allowing you to continue working in the terminal.

### 6. (Optional) View Logs

To view the logs of your services, you can use:

```bash
docker compose logs -f
```

This will tail the logs of all services, allowing you to see the real-time output.

---

Feel free to adapt the instructions based on your specific project structure or additional environment variables that might be required.