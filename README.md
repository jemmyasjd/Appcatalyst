## **Explanation Video : [Click here](https://youtu.be/m_9XBt5dO4c)**

![diagram-export-15-08-2024-12_41_56](https://github.com/user-attachments/assets/3e169d57-17e4-4294-a73b-4ebab35a6a9b)


## INTRODUCTION 🌟

Introducing AppCatalyst, a powerful hosting platform designed for developers to deploy and manage web applications effortlessly.AppCatalyst delivers seamless deployment, real-time updates, and scalable architecture to support modern web development needs.

The project architecture includes various components such as an API server, build server, socket server, and a reverse proxy setup, all orchestrated using AWS services like ECS, ECR, and S3 storage. This setup ensures efficient handling of build processes, real-time updates, and secure storage, making it an good solution for modern web development needs.

## What It Does !! 👷

- Enables developers to deploy websites seamlessly by managing code in 100+ Docker containers for parallel execution.
- Centralizes built files using AWS S3 and ensures real-time communication for instant updates.
- Provides a robust solution with 99.9% uptime for uninterrupted development workflows.

## How I Build 🔧

- **Backend Development:** the backend is developed using Express.js to handle API requests and manage server-side logic.

- **Frontend Development:** The frontend has been developed using the next-js calling the api to the backend.

- **API Server:** The API server was built to handle project creation and task execution, integrating AWS ECS for running tasks and Redis for real-time logging and communication.

- **Build Server:** The build server automates the process of installing dependencies, building the project, and uploading the built files to AWS S3. It uses Redis for real-time logging and AWS SDK for S3 interactions.

- **S3 Reverse Proxy:** Configured a reverse proxy using Express.js and http-proxy to route incoming requests to the appropriate resources stored in AWS S3, ensuring efficient handling of static assets.

- **Real-Time Communication:** Utilized Socket.io to enable real-time updates and communication between the server and clients, ensuring that changes are instantly reflected across the platform.

- **AWS Integration:** Leveraged AWS ECS for container orchestration, ECR for storing Docker images, and S3 for secure and scalable storage of static assets.

- **Containerization:** Created Dockerfiles for each component to containerize the applications, ensuring consistent and isolated environments for deployment.

## Challenges I Ran Into 💀

- **Real-Time Communication:** Initially, I faced difficulties in establishing real-time communication for fetching logs. Ensuring that the logs were updated in real-time required meticulous handling and optimization of the socket server.
- **CORS Errors:** When making POST requests, I encountered CORS (Cross-Origin Resource Sharing) errors. This required updating the server configuration to include appropriate CORS headers, allowing cross-origin requests and resolving the issue.
- **AWS Integration:** Integrating AWS services such as ECS, ECR, and S3 posed challenges, especially in configuring the network and security settings and interacting with the AWS SDK client.

## Architecture Explanation ☣️

- **Frontend to Backend Communication:**
  - The frontend sends a POST request containing the GitHub URL to the backend server.
- **Dynamic Docker Container Creation:**
  - Instead of cloning the GitHub repository directly on the server, the backend spins up a Docker container for each GitHub repository.
  - The code is cloned into these isolated Docker containers, allowing for scalability and parallel execution of multiple repositories.
- **Centralized Storage:**
  - Once the code is cloned and built within the Docker container, the generated output is stored in a centralized AWS S3 bucket.
- **Real-Time Log Streaming:**
  - During the build process, logs are generated and published to Redis.
  - Users can subscribe to these logs via Socket.io, receiving real-time updates on the build status.
- **Accessing Built Files:**
  - After the build process is complete, the built files can be accessed through a reverse proxy, which routes requests to the appropriate resources.
 
## 🔮 Technologies Used:

- AWS ☁️
- Docker 🐳
- Node.js 🟩
- Express.js 🛠️
- Redis 🌀
- Next.js ⚛️
- Socket.io 🌐
- Postman 📮

**🛠️ Explore AppCatalyst:**

Revolutionizing deployment for developers while ensuring security, scalability, and efficiency. Let’s build the future of web development!



