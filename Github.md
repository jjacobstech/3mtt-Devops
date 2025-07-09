# 3MTT DevOps Project Documentation

Welcome to the **3MTT DevOps** project! This repository serves as a comprehensive DevOps learning and implementation project, covering essential aspects of modern DevOps practices and tooling with practical demonstrations.

## Overview

This project demonstrates core DevOps concepts including:
- Continuous Integration / Continuous Deployment (CI/CD)
- Infrastructure as Code (IaC)
- Configuration Management
- Containerization and Orchestration
- Monitoring and Logging
- Automation and Scripting
- Version Control with Git and GitHub
- Development Environment Setup

## Getting Started

### Prerequisites

Before you begin, ensure you have the following:
- Ubuntu system (physical or virtual via VirtualBox)
- Internet connection
- Administrative privileges

### Initial Setup

1. **Clone this repository:**
   ```bash
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
├── docs/                 # Documentation and guides
├── images/               # Screenshots and visual references
└── README.md
```

## Development Environment Setup

### Visual Studio Code Installation on Ubuntu (VirtualBox)

This section walks you through installing **Visual Studio Code (VS Code)** on Ubuntu running inside **VirtualBox**, and preparing it for GitHub integration.

#### 1. Install VS Code on Ubuntu

##### Method 1: Using APT Package Manager

Update your system first:
```bash
sudo apt update && sudo apt upgrade -y
```

Install VS Code using the official Microsoft repository:
```bash
# Add Microsoft GPG key
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

# Update package cache and install
sudo apt update
sudo apt install code
```

##### Method 2: Using Snap Package Manager

```bash
sudo snap install code --classic
```

##### Launch VS Code

After installation, launch VS Code:
```bash
code
```

**Screenshot Example:**  
[![VS Code startup page](images/vscode.png)](images/vscode.png)

#### 2. Essential VS Code Extensions for DevOps

Install these extensions for better DevOps workflow:

```bash
# Install extensions via command line
code --install-extension ms-vscode.vscode-docker
code --install-extension ms-kubernetes-tools.vscode-kubernetes-tools
code --install-extension hashicorp.terraform
code --install-extension ms-vscode.azure-account
code --install-extension amazonwebservices.aws-toolkit-vscode
code --install-extension ms-python.python
code --install-extension ms-vscode.powershell
code --install-extension redhat.ansible
```

## GitHub Account Setup and Configuration

### 1. GitHub Account Setup via Web Management Console

#### Create a GitHub Account

1. Navigate to [https://github.com/](https://github.com/)
2. Click **Sign up** button
3. Fill in your details:
   - Email address
   - Password
   - Username (choose carefully as this will be your GitHub identity)
4. Complete the verification steps (email verification, CAPTCHA)
5. Choose your plan (free plan is sufficient for learning)
6. Complete the initial setup questionnaire

**Screenshot Example:**  
[![GitHub Sign Up Page](images/github.png)](images/github.png)

#### Configure Your GitHub Profile

1. Upload a profile picture
2. Add a bio describing your DevOps journey
3. Set your location and company information
4. Configure your notification preferences

### 2. GitHub Configuration on Ubuntu (VirtualBox)

#### Install Git

Git is essential for version control and GitHub integration:

```bash
sudo apt update
sudo apt install git -y
```

Verify the installation:
```bash
git --version
```

#### Configure Git with Your GitHub Account

Set up your global Git configuration:
```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

Configure additional Git settings:
```bash
# Set default branch name
git config --global init.defaultBranch main

# Set default editor
git config --global core.editor "code --wait"

# Enable colored output
git config --global color.ui auto
```

Verify your configuration:
```bash
git config --list
```

**Screenshot Example:**  
[![Git Config in Ubuntu Terminal](images/github-terminal.png)](images/github-terminal.png)

#### Generate SSH Key for Secure Authentication

Create an SSH key pair for secure GitHub authentication:

```bash
# Generate SSH key (replace with your email)
ssh-keygen -t ed25519 -C "your.email@example.com"

# When prompted, press Enter to accept default file location
# Optionally set a passphrase for added security
```

Start the SSH agent and add your key:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Copy your public SSH key:
```bash
cat ~/.ssh/id_ed25519.pub
```

**Screenshot Example:**  
[![SSH Key Generation in Ubuntu](images/ssh.png)](images/ssh.png)

#### Add SSH Key to GitHub

1. Go to your GitHub account
2. Click on your profile picture → **Settings**
3. Navigate to **SSH and GPG keys**
4. Click **New SSH key**
5. Paste your public key content
6. Give it a descriptive title (e.g., "Ubuntu VirtualBox - DevOps Project")
7. Click **Add SSH key**

**Screenshot Example:**  
[![Add SSH Key to GitHub](images/ssh.png)](images/ssh.png)

#### Test SSH Connection

Verify your SSH connection to GitHub:
```bash
ssh -T git@github.com
```

You should see a message like: "Hi username! You've successfully authenticated..."

## Git Workflow and Best Practices

### Basic Git Operations

#### Clone a Repository
```bash
git clone git@github.com:yourusername/your-repo.git
cd your-repo
```

#### Basic Workflow
```bash
# Check repository status
git status

# Stage changes
git add .

# Commit changes
git commit -m "Descriptive commit message"

# Push changes
git push origin main
```

#### Branching Strategy
```bash
# Create and switch to new branch
git checkout -b feature/new-feature

# Switch between branches
git checkout main
git checkout feature/new-feature

# Merge branch
git checkout main
git merge feature/new-feature

# Delete branch
git branch -d feature/new-feature
```

### DevOps Git Workflow

#### Feature Branch Workflow
1. Create feature branch from main
2. Implement changes
3. Commit with meaningful messages
4. Push branch to remote
5. Create pull request
6. Code review and merge

#### Commit Message Conventions
```
feat: add new monitoring dashboard
fix: resolve container startup issue
docs: update installation guide
test: add unit tests for API endpoints
ci: update GitHub Actions workflow
```

## AWS Integration (Optional)

### AWS CLI Installation and Configuration

#### Install AWS CLI
```bash
# Download and install AWS CLI v2
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

#### Configure AWS CLI
```bash
aws configure
```

Enter your:
- AWS Access Key ID
- AWS Secret Access Key
- Default region (e.g., us-east-1)
- Default output format (json)

#### Verify AWS Configuration
```bash
aws sts get-caller-identity
```

## VirtualBox Optimization for DevOps

### System Requirements
- Minimum 4GB RAM (8GB recommended)
- 20GB+ disk space
- Enable virtualization in BIOS/UEFI

### Performance Optimization
```bash
# Install VirtualBox Guest Additions
sudo apt update
sudo apt install build-essential dkms linux-headers-$(uname -r)

# Mount Guest Additions CD and install
sudo mkdir /media/cdrom
sudo mount /dev/cdrom /media/cdrom
sudo sh /media/cdrom/VBoxLinuxAdditions.run
```

### Shared Folders Setup
1. In VirtualBox, go to Settings → Shared Folders
2. Add a new shared folder
3. Mount in Ubuntu:
```bash
sudo mkdir /mnt/shared
sudo mount -t vboxsf ShareName /mnt/shared
```

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create your feature branch:**
   ```bash
   git checkout -b feature/my-feature
   ```
3. **Commit your changes:**
   ```bash
   git commit -am 'Add some feature'
   ```
4. **Push to the branch:**
   ```bash
   git push origin feature/my-feature
   ```
5. **Open a Pull Request**

### Contribution Guidelines

- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Ensure all CI/CD checks pass
- Write clear commit messages

## Troubleshooting

### Common Issues

#### Git Authentication Issues
```bash
# If you get permission denied
ssh-add ~/.ssh/id_ed25519

# Test SSH connection
ssh -T git@github.com
```

#### VS Code Extensions Not Working
```bash
# Reset VS Code extensions
code --reset-extensions
```

#### VirtualBox Performance Issues
- Increase allocated RAM
- Enable hardware acceleration
- Install Guest Additions

## Next Steps

1. **Set up your development environment** following this guide
2. **Explore the project structure** and understand each component
3. **Practice basic Git operations** with sample repositories
4. **Implement CI/CD pipelines** using the provided configurations
5. **Deploy infrastructure** using Terraform or CloudFormation
6. **Set up monitoring** and logging solutions
7. **Contribute to the project** by adding new features or improvements

## Resources and Learning Materials

### Official Documentation
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com/)
- [VS Code Documentation](https://code.visualstudio.com/docs)
- [Docker Documentation](https://docs.docker.com/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)

### DevOps Learning Paths
- DevOps fundamentals
- Infrastructure as Code
- Container orchestration
- Monitoring and observability
- Security best practices

---

## Download This Documentation

To download this documentation as a markdown file:

1. **Direct download**: Right-click on the artifact and select "Save as" or "Download"
2. **Copy content**: Copy the entire content and save it as `README.md` or `DevOps-Guide.md`
3. **GitHub integration**: Use this content to create a comprehensive README for your DevOps repository

### File Structure for Download
```
3mtt-devops-documentation/
├── README.md (this file)
├── images/
│   ├── vscode.png
│   ├── github.png
│   ├── github-terminal.png
│   └── ssh.png
└── docs/
    ├── setup-guide.md
    ├── git-workflow.md
    ├── aws-integration.md
    └── troubleshooting.md
```

---
