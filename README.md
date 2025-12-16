# CI/CD Pipeline using Jenkins, Docker & AWS ECR

## 📌 Project Overview
This project demonstrates a complete Continuous Integration (CI) pipeline built using Jenkins.  
The pipeline automatically pulls source code from GitHub, builds a Docker image, and pushes the image to AWS Elastic Container Registry (ECR).

This project focuses on **real-world DevOps practices**, including troubleshooting and pipeline automation.

---

## 🏗️ Architecture
GitHub → Jenkins (EC2) → Docker → AWS ECR

---

## 🛠️ Tools & Technologies Used
- **AWS EC2** (Amazon Linux 2023)
- **Jenkins**
- **Docker**
- **AWS Elastic Container Registry (ECR)**
- **AWS IAM**
- **Git & GitHub**

---

## 🔄 CI Pipeline Workflow
1. Jenkins pulls source code from GitHub  
2. Docker image is built using a Dockerfile  
3. Jenkins authenticates to AWS ECR  
4. Docker image is tagged  
5. Image is pushed to AWS ECR  

---

## ⚙️ Jenkins Pipeline (Jenkinsfile)
The pipeline is written using Jenkins Declarative Pipeline syntax and includes stages for:
- Code checkout
- Docker build
- AWS ECR login
- Image tagging
- Image push

---

## 🚧 Challenges Faced & How I Resolved Them

### 🔹 Jenkins Node Offline (Disk Space Issue)
- **Issue:** Jenkins blocked builds due to low disk space on `/tmp`
- **Solution:** Configured a custom Java temporary directory using systemd override

---

### 🔹 Docker Permission Denied Error
- **Issue:** Jenkins user could not access Docker daemon
- **Solution:** Adjusted Docker socket permissions for CI environment

---

### 🔹 Git Checkout Failure
- **Issue:** Jenkins tried to build `master` branch while repository used `main`
- **Solution:** Explicitly specified `main` branch in Jenkins pipeline

---

### 🔹 AWS Authentication Failure
- **Issue:** Incorrect Jenkins credential type used for AWS
- **Solution:** Recreated credentials using **AWS Credentials** type

---

## ✅ Final Outcome
- Docker image successfully built by Jenkins
- Image pushed to AWS ECR
- Fully functional CI pipeline achieved

---

## 👩‍💻 Author
**Shikha Mathur**  
Aspiring Cloud & DevOps Engineer
