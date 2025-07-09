# 3mtt-Devops

Welcome to the **3mtt-Devops** project!  
This repository serves as a practical DevOps project, covering the essential aspects of modern DevOps practices and tooling.

## Overview

This project demonstrates core DevOps concepts including:
- Continuous Integration / Continuous Deployment (CI/CD)
- Infrastructure as Code (IaC)
- Configuration Management
- Containerization and Orchestration
- Monitoring and Logging
- Automation and Scripting

## Getting Started

### Prerequisites

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [Kubernetes](https://kubernetes.io/) or [Minikube](https://minikube.sigs.k8s.io/)
- [Terraform](https://www.terraform.io/) (for IaC)
- [Ansible](https://www.ansible.com/) or similar tool (for configuration management)
- [Python](https://www.python.org/) or [Bash](https://www.gnu.org/software/bash/) (for scripting)
- Cloud provider CLI (e.g., AWS CLI, Azure CLI, or GCP CLI), if deploying to the cloud

### Setup

1. **Clone this repository:**
   ```sh
   git clone https://github.com/jjacobstech/3mtt-Devops.git
   cd 3mtt-Devops
   ```

2. **Review the documentation and folder structure** for various DevOps components.

3. **Set up environment variables** as required for your environment.

## Project Structure

```
.
├── ci-cd/                # CI/CD pipeline configurations (GitHub Actions, Jenkins, etc.)
├── infrastructure/       # Infrastructure as Code (Terraform, CloudFormation, etc.)
├── config-management/    # Configuration management scripts/playbooks
├── scripts/              # Automation scripts (Python, Bash, etc.)
├── containers/           # Dockerfiles and container configuration
├── k8s/                  # Kubernetes manifests
├── monitoring/           # Monitoring and logging configurations
└── README.md
```

## Workflows

- **CI/CD:** Automated build, test, and deployment pipelines.
- **IaC:** Provision and manage infrastructure declaratively.
- **Config Management:** Maintain consistency across environments.
- **Containerization:** Build and deploy applications using Docker and Kubernetes.
- **Monitoring:** Collect, analyze, and visualize metrics and logs.

## Contributing

Contributions are welcome! Please open issues and submit pull requests for improvements, bug fixes, or new features.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

# GitHub Account Setup: Web Console and Ubuntu (VirtualBox)

This document demonstrates setting up a GitHub account using the web management console and configuring it on Ubuntu running inside VirtualBox.

---

## 1. GitHub Account Setup via Web Management Console

### a. Sign Up for a GitHub Account

1. Go to [https://github.com/](https://github.com/).
2. Click **Sign up**.
3. Fill in your email address, create a password, and set your username.
4. Complete the verification steps.
5. Choose your plan (you can start with the free plan).

**Screenshot Example:**  
[![GitHub Sign Up Page](images/github-signup.png)](images/github-signup.png)

---

## 2. GitHub Configuration on Ubuntu (VirtualBox)

### a. Install Git

Open your Ubuntu terminal and run:
```bash
sudo apt update
sudo apt install git
```

### b. Configure Git with Your GitHub Account

Replace your details below:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

To confirm your configuration:
```bash
git config --list
```

**Screenshot Example:**  
[![Git Config in Ubuntu Terminal](images/git-config-ubuntu.png)](images/git-config-ubuntu.png)

### c. Generate SSH Key (Recommended)

```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
# Press enter to accept defaults
```

Add your SSH key to the SSH agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Copy your public SSH key:
```bash
cat ~/.ssh/id_ed25519.pub
```

**Screenshot Example:**  
[![SSH Key Generation in Ubuntu](images/ssh-keygen-ubuntu.png)](images/ssh-keygen-ubuntu.png)

### d. Add SSH Key to GitHub

1. Go to your GitHub account.
2. Click on your profile picture → **Settings** → **SSH and GPG keys**.
3. Click **New SSH key**, paste your public key, and save.

**Screenshot Example:**  
[![Add SSH Key to GitHub](images/add-sshkey-github.png)](images/add-sshkey-github.png)

---

## 3. Clone a Repository to Ubuntu

```bash
git clone git@github.com:yourusername/your-repo.git
cd your-repo
```

---

## Artifacts

- [`images/github-signup.png`](images/github-signup.png): Screenshot of GitHub sign-up page.
- [`images/git-config-ubuntu.png`](images/git-config-ubuntu.png): Terminal showing Git configuration.
- [`images/ssh-keygen-ubuntu.png`](images/ssh-keygen-ubuntu.png): Terminal showing SSH key generation.
- [`images/add-sshkey-github.png`](images/add-sshkey-github.png): Screenshot of adding SSH key on GitHub.

---
