# Node.js CI/CD Demo App

This repository demonstrates a **CI/CD pipeline** using **GitHub Actions** to automatically build, Dockerize, and push a Node.js application to DockerHub.

---

## Features
- Simple Node.js Express app
- Dockerized for container deployment
- Automated CI/CD workflow with GitHub Actions
- Push → Build → DockerHub workflow

---

## Project Structure
.
├── Dockerfile
├── index.js
├── package.json
├── package-lock.json
└── .github/workflows/main.yml

yaml
Copy code

---

## How CI/CD Works
1. On every push to the `main` branch:
   - The workflow installs dependencies (`npm install`)
   - Runs tests (currently placeholder)
   - Builds a Docker image
   - Pushes the image to DockerHub

2. Docker image is available at:  
`syedabdulrahman134/nodejs-demo-app:latest`

---

## Setup Locally

1. Clone the repository:
```bash
git clone https://github.com/SYED-ABDULRAHMAN/nodejs-demo-app.git
cd nodejs-demo-app
Install dependencies:

bash
Copy code
npm install
Run the app locally:

bash
Copy code
node index.js
Open http://localhost:3000 in your browser.

Test Docker Image Locally
bash
Copy code
docker build -t nodejs-demo-app .
docker run -p 3000:3000 nodejs-demo-app
GitHub Actions Workflow
Workflow file: .github/workflows/main.yml

Triggers: Push to main branch

Steps:

Checkout code

Set up Node.js

Install dependencies

Run tests

Build Docker image

Login to DockerHub

Push Docker image

Secrets Configuration
Add the following GitHub secrets to enable DockerHub push:

DOCKER_USERNAME → Your DockerHub username

DOCKER_PASSWORD → Your DockerHub password

