🚀 Docker Permission Troubleshooting in WSL — DevOps Hands-On Project










📘 Project Summary

This DevOps project documents my complete hands-on experience troubleshooting Docker permission issues inside WSL (Windows Subsystem for Linux).

I intentionally executed real DevOps tasks, encountered real errors, debugged them step-by-step, and built a custom Docker image — just like real-world DevOps engineering work.

This repository contains:

✔ Docker permission troubleshooting
✔ sudo vs non-sudo execution
✔ docker.sock daemon explanation
✔ Fix for "permission denied"
✔ Custom Dockerfile (Nginx)
✔ Running custom Docker containers
✔ Professional documentation (PDF + DOCX)

📂 Repository Structure
docker-permission-troubleshooting/
│
├── Docker_LinkedIn_Carousel_Regenerated.pdf   # LinkedIn-ready carousel
├── DevOps_Docker_Permission_Document.docx     # Full technical documentation
├── README.md                                   # This file
└── screenshots/                                # Add your screenshots here

🧩 What I Learned in This Project
🐳 Docker Fundamentals

Running containers

Pulling images

Understanding Docker daemon

🔐 Linux Permission Concepts

Why Docker needs sudo

Who owns /var/run/docker.sock

Why normal users get permission denied

Docker group permissions

🛠 Troubleshooting Skills

Identifying root cause

Fixing permission denied error

Running Docker without sudo

🧱 Dockerfile Skills

Writing Dockerfile

Fixing syntax errors

Building custom images

Running custom Nginx image

❗ Errors Encountered & Fixes
1️⃣ Error: Running Docker Without sudo
permission denied while trying to connect to the Docker daemon socket

📌 Reason:

Docker daemon runs as root

/var/run/docker.sock belongs to root:docker

Normal users cannot access daemon

🖼 Screenshot Placeholder:
[screenshots/permission-denied.png]

2️⃣ Error: Dockerfile Parse Error
Error: FROM requires one or three arguments

📌 Reason:

Incorrect:

FROM nginx: latest


Correct:

FROM nginx:latest

🖼 Screenshot Placeholder:
[screenshots/dockerfile-error.png]

🛠 Fix Implemented
✔ Add User to Docker Group
sudo usermod -aG docker $USER
newgrp docker

Why this works:

Grants permission to access docker.sock

Allows Docker commands without sudo

Makes Docker usable for developer environments

🖼 Screenshot Placeholder:
[screenshots/group-added.png]

🐳 Successfully Running Docker Without sudo

Commands tested:

docker run hello-world
docker ps
docker images

🖼 Screenshot Placeholder:
[screenshots/docker-success.png]

🖥️ Custom Dockerfile Built in This Project
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html

Build & Run
docker build -t shiva-custom-nginx .
docker run -d --name custom-web -p 8081:80 shiva-custom-nginx

🖼 Screenshot Placeholder:
[screenshots/custom-nginx.png]

📄 Documentation Included

✔ Docker_LinkedIn_Carousel_Regenerated.pdf
✔ DevOps_Docker_Permission_Document.docx

Documentation contains:

Errors

Root causes

Fixes

Screenshots

Docker commands

Full explanations

🌐 Final Output Example
Hello Shiva! This is your first custom Docker image!


Served via an Nginx Docker container.

🎯 Skills Demonstrated

Linux user/group management

WSL troubleshooting

Docker daemon understanding

Dockerfile creation & debugging

Containerization best practices

Git & GitHub workflow

Documentation writing

DevOps problem-solving

🧑‍💻 Author

Shiva Ponnam
DevOps Engineer | Docker | Linux | AWS | CI/CD | GitHub
🔗 GitHub: https://github.com/Shiva-77-P

🔗 LinkedIn: https://linkedin.com/in/**your-profile
**

⭐ How to Use This Repository
git clone https://github.com/Shiva-77-P/docker-permission-troubleshooting.git
cd docker-permission-troubleshooting
