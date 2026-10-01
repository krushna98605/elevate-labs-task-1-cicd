\# Elevate Labs Task 1 — CI/CD Pipeline with GitHub Actions



\## Overview



This project demonstrates an automated CI/CD pipeline for a Node.js web application using GitHub Actions and Docker.



The pipeline automatically:



1\. Checks out the source code.

2\. Sets up Node.js.

3\. Installs project dependencies.

4\. Runs tests.

5\. Authenticates with Docker Hub.

6\. Builds the Docker image.

7\. Pushes the Docker image to Docker Hub.



\## Technologies Used



\- Node.js

\- Express.js

\- Docker

\- Docker Hub

\- GitHub Actions

\- Git



\## Project Structure



```text

elevate-labs-task-1-cicd/

├── .github/

│   └── workflows/

│       └── main.yml

├── .dockerignore

├── .gitignore

├── Dockerfile

├── app.js

├── package.json

├── package-lock.json

└── README.md

```



\## Application



The application is a simple Express.js web server.



\### Endpoints



\- `GET /` — Returns a welcome message.

\- `GET /health` — Returns the application health status.



Run locally:



```bash

npm install

npm start

```



The application runs on:



```text

http://localhost:3000

```



Health check:



```text

http://localhost:3000/health

```



\## Docker



Build the Docker image:



```bash

docker build -t elevate-labs-task-1-cicd .

```



Run the container:



```bash

docker run -p 3000:3000 elevate-labs-task-1-cicd

```



\## CI/CD Workflow



The GitHub Actions workflow is located at:



```text

.github/workflows/main.yml

```



It runs when code is pushed to or a pull request targets the `main` branch.



\### Pipeline Flow



```text

Developer pushes code

&#x20;       ↓

GitHub Repository

&#x20;       ↓

GitHub Actions

&#x20;       ↓

Checkout Code

&#x20;       ↓

Setup Node.js

&#x20;       ↓

Install Dependencies

&#x20;       ↓

Run Tests

&#x20;       ↓

Login to Docker Hub

&#x20;       ↓

Build Docker Image

&#x20;       ↓

Push Image to Docker Hub

```



\## GitHub Secrets



The workflow uses GitHub Actions secrets so credentials are not stored in the source code.



Required secrets:



```text

DOCKERHUB\_USERNAME

DOCKERHUB\_TOKEN

```



The Docker Hub access token should have permission to push images.



\## Docker Hub Image



Docker Hub repository:



`krushnadevops9860/elevate-labs-task-1-cicd`



The `latest` image is automatically updated by the GitHub Actions pipeline after a successful push to `main`.



\## Result



The CI/CD pipeline successfully automates testing, Docker image creation, and Docker Hub deployment.



This demonstrates a basic DevOps workflow where application changes can be automatically validated, containerized, and published using GitHub Actions.



\## Learning Outcomes



\- Understanding CI/CD concepts

\- Creating GitHub Actions workflows

\- Using GitHub Actions runners

\- Automating Node.js dependency installation and testing

\- Building Docker images

\- Authenticating securely with Docker Hub

\- Automatically publishing Docker images

\- Managing CI/CD secrets



