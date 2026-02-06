# Devops-starter

A streamlined CI/CD pipeline project demonstrating automated deployment of a web application to AWS EC2 using Docker and GitHub Actions.

---

## 🚀 Project Overview
This project serves as a foundational **DevOps Starter** template. The primary goal is to automate the deployment process: whenever a change is made to the source code (like the `index.html` file), a GitHub Actions workflow automatically builds a new container image and deploys it to an AWS EC2 instance.

## 🛠 Tech Stack
* **Frontend:** HTML
* **Containerization:** Docker
* **CI/CD:** GitHub Actions
* **Registry:** Docker Hub
* **Cloud Provider:** AWS (EC2)

## 🏗 Architecture
The automation pipeline follows these steps:
1.  **Code Update:** Developer pushes changes to the `main` branch.
2.  **Build Phase:** GitHub Actions triggers a workflow to build a fresh Docker image.
3.  **Push Phase:** The newly built image is pushed to **Docker Hub**.
4.  **Deployment Phase:** GitHub Actions SSHes into the **AWS EC2** instance, pulls the latest image, stops the existing container, and runs the updated application.

## 📁 Repository Structure
* `index.html`: The web application's entry point.
* `Dockerfile`: Instructions to containerize the application.
* `.github/workflows/`: YAML configuration for the CI/CD pipeline.

## ⚙️ Setup & Configuration

### Prerequisites
* An AWS account with an active EC2 instance.
* Docker Hub account and repository.
* GitHub Repository Secrets configured for:
    * `DOCKER_HUB_USERNAME`
    * `DOCKER_HUB_ACCESS_TOKEN` or `DOCKER_HUB_PASSWORD`
    * `EC2_HOST` (Public IP of your instance)
    * `EC2_USER` (e.g., `ubuntu` or `ec2-user`)
    * `EC2_SSH_KEY` (Your private `.pem` key)

### How to use
1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/BKY1601/Devops-starter.git](https://github.com/BKY1601/Devops-starter.git)
    ```
2.  **Modify the content:** Update `index.html` with your custom content.
3.  **Push to GitHub:**
    ```bash
    git add .
    git commit -m "Update website content"
    git push origin main
    ```
4.  **Verify:** Check the **Actions** tab in GitHub to see the deployment progress. Once finished, visit your EC2 Public IP to see the changes live!

---

## 👨‍💻 Author

**Bipin Yadav**  
📧 bipinyadav919@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/bipin-yadav-jan16)  
🔗 [GitHub](https://github.com/BKY1601)                                         

---

*Created as part of my journey as a Cloud Engineer.*
