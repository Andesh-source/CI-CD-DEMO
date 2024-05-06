## Setting Up CI/CD Pipeline with GitHub Actions and EC2 Instance

This guide will walk you through the process of setting up a CI/CD pipeline using GitHub Actions, an EC2 instance running Ubuntu, and Nginx as the server.

### Prerequisites

- An AWS account with access to EC2 services.
- Basic familiarity with AWS EC2 and GitHub.
- An EC2 instance running Ubuntu with Nginx installed.
- A GitHub account with a repository containing your code.

### Step 1: Set Up Your EC2 Instance

1. **Launch an EC2 instance on AWS with Ubuntu as the operating system.**
2. **Configure the security groups to allow incoming traffic on port 22 (SSH) and port 80 (HTTP).**
3. **Connect to your EC2 instance using SSH.**

### Step 2: Install and Configure Nginx

1. **Update the system packages:**
    sudo apt update && sudo apt upgrade -y


2. **Install Nginx:**

    sudo apt install nginx -y


3. **Start the Nginx service:**

    sudo systemctl start nginx


### Step 3: Set Up SSH Key-Based Authentication

1. **Generate an SSH key pair on your EC2 instance (if not already done):**

    ssh-keygen -t rsa -b 4096


2. **Press Enter to save the key pair in the default location.**

3. **Copy the public key to the clipboard:**

    cat ~/.ssh/id_rsa.pub


4. **Add the public key to your GitHub account:**
- **Go to your GitHub account settings.**
- **Select "SSH and GPG keys."**
- **Click on "New SSH key" and paste the copied public key into the provided field.**

### Step 4: Set Up Your GitHub Repository

1. **Create a new repository or navigate to an existing repository on GitHub.**

2. **Clone the repository to your EC2 instance using SSH:**

    git clone git@github.com:<username>/<repository>.git


**Replace `<username>` with your GitHub username and `<repository>` with your repository name.**

### Step 5: Configure GitHub Actions

1. **Inside your cloned repository on the EC2 instance, navigate to the root directory of your repository.**

2. **Create a new directory named `.github` if it doesn't exist:**

    mkdir .github


3. **Change into the `.github` directory:**

    cd .github


4. **Create a new directory named `workflows` inside the `.github` directory:**

    mkdir workflows


5. **Change into the newly created `workflows` directory:**

    cd workflows


6. **Create a new file with the `.yml` extension (e.g., `deploy.yml`) to define your deployment workflow:**

    touch deploy.yml

7. **Edit the file and add the desired YAML code, such as the one provided in your previous message, to define your deployment workflow. Customize the script section of the YAML file to match your specific deployment requirements, such as the path to your code and any additional build or configuration steps needed for your application. Save the file.**

### Step 6: Configure GitHub Secrets

1. **Go to your GitHub repository.**

2. **Navigate to "Settings" > "Secrets".**

3. **Click on "New Repository Secret".**

4. **Name the secret `SSH_PRIVATE` and paste your private SSH key into the "Value" field.**

5. **Click on "Add Secret" to save it.**

### Step 7: Test Your Deployment Pipeline

1. **Commit and push your changes to the GitHub repository.**

2. **Navigate to the "Actions" tab in your GitHub repository to view the workflow execution.**

3. **Monitor the logs to ensure that the deployment steps are executed successfully.**

4. **Access your EC2 instance's public IP address in a web browser to verify that the updated code is deployed and visible.**

Congratulations! You have successfully set up a CI/CD pipeline using GitHub Actions, an EC2 instance running Ubuntu, and Nginx as the server.

Feel free to customize the document as per your requirements, adding any additional information or clarifications necessary for your specific setup.
