Overview
This project aims to automate the deployment of a lightweight Kubernetes distribution (k3s) on AWS using GitHub Actions for orchestration, Pulumi for infrastructure as code (IaC), and Ansible for configuration management.

Key Components
GitHub Actions: Automates workflows triggered by events in GitHub repositories.
Pulumi: Infrastructure as Code tool to provision AWS resources.
Ansible: Configuration management tool for installing and configuring k3s on AWS EC2 instances.
Prerequisites
Before proceeding, ensure you have the following:

An AWS account with appropriate IAM permissions.
Pulumi CLI installed locally and authenticated with your Pulumi account and a PULUMI access token.
GitHub repository set up to host your Pulumi project.
Access to GitHub Secrets to securely store credentials and sensitive information.

Project Structure
The project is organized into the following structure:

K3s-deployment-automation/
├── Infra/                    # Pulumi project directory
│   ├── __main__.py           # Pulumi Python script defining AWS resources
│   ├── Pulumi.dev.yaml
│   ├── Pulumi.yaml
│   ├── requirements.txt
│   ├── venv/                 # Virtual environment for Python dependencies 
│   └── ...                   # Other Pulumi project files and configurations
├── .github/                  # GitHub Actions workflows directory
│   └── workflows/
│       ├── infra.yml         # GitHub Actions workflow for deploying infrastructure
│       └── setup-git-runner.yml    # GitHub Actions workflow for deploying K3s
├── ...                       # Other project files and directories

Deployment Process
The deployment process involves the following steps:

GitHub Actions 1: A GitHub Actions workflow is triggered by a push event to the main branch
Pulumi: The Pulumi Python script is executed to provision the AWS resources
GitHub Action 2: A second GitHub Actions workflow is triggered to install self-hosted Git runner and install Ansible in the Git-runner public instance making it the control node for Ansible automation
GitHUb Action 3: The Ansible playbook is executed to install and configure k3s on the private EC2 instances.