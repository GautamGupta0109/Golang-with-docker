Dockerized Go Application
📌 Overview

This project demonstrates how to run a Go (Golang) application inside a Docker container without manually installing dependencies like Ubuntu, Go, or other system packages on your local machine.

Instead of setting up everything locally, we pull a prebuilt Docker image that already contains the required environment. This saves time and ensures consistency across systems.

⚙️ How It Works

A base Docker image (with Go/Ubuntu) is pulled from a registry.

A working directory (WORKDIR) is created inside the container.

The application source code is copied into the container.

The Go application is built into an executable.

The container runs the compiled binary.

📁 Project Structure
.
├── main.go        # Simple Go server
├── Dockerfile     # Instructions to build the Docker image
└── README.md      # Documentation
📄 main.go

This file contains a basic Go server. It listens on a port and serves requests.

🐳 Dockerfile Explanation

The Dockerfile performs the following steps:

Pulls a base image
This image includes Go and necessary tools.

Creates a working directory

WORKDIR /app

Copies project files

COPY . .

Builds the Go application

RUN go build -o app

Runs the executable

CMD ["./app"]
🚀 How to Run the Project
1. Build the Docker Image
docker build -t docker-test .
2. Verify Image Creation
docker image ls
3. Run the Docker Container
docker run -p 8080:8081 -it docker-test

-p 8080:8081 → Maps port 8081 (container) to 8080 (host)

-it → Interactive terminal

🌐 Access the Application

Once the container is running, open your browser and go to:

http://localhost:8080
💡 Key Concepts

Docker Image: Prebuilt environment with dependencies

Container: Running instance of an image

WORKDIR: The main working directory inside the container (very important)

Port Mapping: Connects container ports to your local machine

✅ Benefits of This Setup

No need to install Go or Ubuntu locally

Consistent environment across machines

Easy to build, run, and share

Faster onboarding for new developers

📌 Notes

Make sure Docker is installed and running

Ensure ports are not already in use

Modify ports if needed

🧪 Future Improvements

Add Docker Compose

Add environment variables support

Add multi-stage builds for smaller images

Happy coding! 🚀
