# Development Environment Setup Project

## Project Overview
This project demonstrates the setup and configuration of essential development tools and environments required for modern software development workflows.

## Objectives
This assignment aims to demonstrate proficiency in:
1. Setting up and configuring development environments
2. Installing and using version control systems
3. Configuring cloud development platforms
4. Implementing DevOps best practices
5. Documenting setup processes with visual confirmation

## Required Tools & Platforms

### Development Tools
- **Visual Studio Code**: Primary code editor with extensions
- **Git**: Version control system
- **VirtualBox**: Virtualization platform for testing environments
- **Ubuntu**: Linux distribution for development

### Accounts & Services
- **GitHub**: Version control hosting and collaboration
- **AWS Management Console**: Cloud services platform

## Setup Instructions

### 1. Visual Studio Code Installation
1. Download VS Code from [official website](https://code.visualstudio.com/)
2. Install with default settings
3. Install recommended extensions for your development stack
4. **Screenshot Required**: VS Code welcome screen showing successful installation

### 2. Git Configuration
1. Install Git from [git-scm.com](https://git-scm.com/)
2. Configure user information:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
3. Verify installation:
   ```bash
   git --version
   ```
4. **Screenshot Required**: Terminal showing `git --version` command output

### 3. VirtualBox Setup
1. Download VirtualBox from [official website](https://www.virtualbox.org/)
2. Install following system-specific instructions
3. Create a new virtual machine
4. **Screenshot Required**: VirtualBox main interface

### 4. Ubuntu Installation
1. Download Ubuntu ISO from [ubuntu.com](https://ubuntu.com/)
2. Create Ubuntu VM in VirtualBox or install natively
3. Complete initial setup and user configuration
4. **Screenshot Required**: Ubuntu desktop showing successful login

### 5. GitHub Account Setup
1. Create account at [github.com](https://github.com/) if not already done
2. Set up SSH keys for secure authentication:
   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```
3. Add SSH key to GitHub account
4. **Screenshot Required**: GitHub dashboard showing account profile

### 6. AWS Management Console Access
1. Create AWS account at [aws.amazon.com](https://aws.amazon.com/)
2. Complete account verification process
3. Access AWS Management Console
4. Familiarize yourself with basic services (EC2, S3, IAM)
5. **Screenshot Required**: AWS Management Console main dashboard

## Documentation Requirements

### Screenshots Checklist
Ensure all screenshots include:
- [ ] VS Code welcome screen
- [ ] Terminal with `git --version` output
- [ ] VirtualBox main interface
- [ ] Ubuntu desktop after login
- [ ] GitHub dashboard/profile page
- [ ] AWS Management Console main page

### Screenshot Guidelines
- Use clear, high-resolution images
- Include relevant timestamps where possible
- Ensure all UI elements are visible and readable
- Save screenshots in a dedicated `/screenshots` folder
- Name files descriptively (e.g., `vscode_welcome.png`, `git_version.png`)

## Project Structure
```
project-root/
├── README.md
├── screenshots/
│   ├── vscode_welcome.png
│   ├── git_version_terminal.png
│   ├── virtualbox_interface.png
│   ├── ubuntu_desktop.png
│   ├── github_dashboard.png
│   └── aws_console.png
├── setup-scripts/
│   ├── install_dependencies.sh
│   └── configure_git.sh
└── documentation/
    ├── troubleshooting.md
    └── additional_resources.md
```

## Verification Steps

### Self-Check Before Submission
1. **All tools installed**: Verify each application launches successfully
2. **Screenshots captured**: All required screenshots are clear and complete
3. **Accounts accessible**: Can log into GitHub and AWS without issues
4. **Git configured**: Can clone repositories and make commits
5. **Documentation complete**: README includes all setup steps and evidence

## Troubleshooting

### Common Issues
- **Git not recognized**: Ensure Git is added to system PATH
- **VirtualBox installation fails**: Check system virtualization settings
- **AWS account verification**: May take 24-48 hours for full activation
- **SSH key issues**: Verify key is properly added to GitHub account

## Additional Resources
- [Git Documentation](https://git-scm.com/doc)
- [VS Code Getting Started](https://code.visualstudio.com/docs)
- [VirtualBox User Manual](https://www.virtualbox.org/manual/)
- [Ubuntu Desktop Guide](https://help.ubuntu.com/stable/ubuntu-help/)
- [GitHub Documentation](https://docs.github.com/)
- [AWS Getting Started](https://aws.amazon.com/getting-started/)

## Submission Checklist
- [ ] All required software installed and functioning
- [ ] All account setups completed
- [ ] Screenshots captured and included
- [ ] README documentation complete
- [ ] Repository properly organized
- [ ] All objectives addressed with visual confirmation

## Notes
This project serves as the foundation for future development work. Proper setup and documentation of these tools will streamline subsequent assignments and real-world development tasks.

---

**Important**: This submission must demonstrate actual setup and configuration, not just template content. All screenshots and documentation should reflect your specific installations and account setups.
