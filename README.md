# WhisperZone

A real-time chat application using Flask, Redis, MongoDB, Flask-SocketIO, and a React frontend powered by Vite. This application supports room-based chats with Redis for in-memory message storage and MongoDB for persistent chat history.

This project began as a demo for practicing DevOps and has now been made public for Hacktoberfest. Contributions and feature suggestions are welcome!

**(Hacktoberfest)**
I'm open to new feature ideas! If you have any cool features you'd like to implement, open an issue, and I'll assign it to you so you can start working on it.

## Features

- **Real-time communication** using WebSockets via Flask-SocketIO.
- **Room-based chat system** with dynamically generated room codes.
- **In-memory chat storage** using Redis and **persistent chat history** saved in MongoDB.
- **REST API endpoints** to create and join chat rooms, and save chat history.
- **React frontend** for user-friendly chat experience.
- Dockerized setup with Redis, MongoDB, Flask backend, and React frontend running in containers.
- Integration tests for Redis, MongoDB connectivity, and API functionality.

## Prerequisites

Ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Node.js](https://nodejs.org/) (for frontend development)
- Python 3.12.3 (for local backend development and testing)

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/navaneethkrishna30/WhisperZone.git
cd WhisperZone
```

### Setup Docker Secrets

Create a `.env` file in the project root and define the following secrets:

```
REDIS_PASSWORD=your_redis_password
MONGO_INITDB_ROOT_USERNAME=your_mongo_username
MONGO_INITDB_ROOT_PASSWORD=your_mongo_password
```

## Running the Application with Docker

### Backend Services

This project uses Docker Compose to manage services (backend, Redis, MongoDB).

1. **Build and start the services:**

   ```bash
   docker compose -f compose.local.yaml up --build
   ```

   This will start the backend, Redis, MongoDB, in their respective containers. The backend will be exposed on port `5000`.
   
2. **Access the application:**

   - The backend API will be available at `http://localhost:5000`.

### Frontend Development

The frontend is built using Vite and React, located in the `frontend/` directory.

To run the frontend locally (without Docker), follow these steps:

1. Navigate to the `frontend/` directory:

   ```bash
   cd frontend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the development server:

   ```bash
   npm run dev
   ```

   The frontend will now be available at `http://localhost:5173`.

## Running Tests

The application includes integration tests for Redis, MongoDB, and API routes. To run the tests:

1. **Ensure Docker secrets are set for testing** (e.g., `REDIS_PASSWORD`, `MONGO_USER`, `MONGO_PASSWORD`).

2. **Run the tests:**

   ```bash
   docker-compose -f compose-test.yaml up --build --abort-on-container-exit
   ```

   This will start the backend in test mode and automatically run the tests.

## Docker Services

The application is divided into the following services:

1. **Backend:**
   - Flask app with WebSocket support via Flask-SocketIO.
   - Manages chat rooms and messages.
   - REST API for creating/joining rooms and saving chat history.

2. **Redis:**
   - Used for real-time, in-memory message storage and room management.

3. **MongoDB:**
   - Used for saving persistent chat history.

## Contributing

We welcome contributions from the community. To get started:

1. **Fork the repository.**
2. **Create a feature branch:**
   ```bash
   git checkout -b feature/my-feature
   ```
3. **Make your changes.**
4. **Run tests locally.**
5. **Push the changes to your fork.**
6. **Submit a pull request.**


## Reporting Issues

If you encounter any bugs or have suggestions for improvements, please open an issue on GitHub.