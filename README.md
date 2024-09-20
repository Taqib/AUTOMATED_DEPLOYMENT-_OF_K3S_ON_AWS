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