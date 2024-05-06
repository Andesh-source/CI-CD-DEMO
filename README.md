## Setting Up CI/CD Pipeline with GitHub Actions and EC2 Instance

This guide will walk you through the process of setting up a CI/CD pipeline using GitHub Actions to deploy changes from your local machine to an EC2 instance running Ubuntu with Nginx.

### Prerequisites

- An AWS account with access to EC2 services.
- Basic familiarity with AWS EC2 and GitHub.
- An EC2 instance running Ubuntu with Nginx installed.
- A GitHub account with a repository containing your code.

### Step 1: Set Up Your EC2 Instance

1. Launch an EC2 instance on AWS with Ubuntu as the operating system.
2. Configure the security groups to allow incoming traffic on port 22 (SSH) and port 80 (HTTP).
3. Connect to your EC2 instance using SSH.

### Step 2: Install and Configure Nginx

1. Update the system packages:

    sudo apt update && sudo apt upgrade -y


2. Install Nginx:

    sudo apt install nginx -y


3. Start the Nginx service:

    sudo systemctl start nginx


### Step 3: Set Up Your GitHub Repository

1. Create a new repository or navigate to an existing repository on GitHub.

2. Clone the repository to your local machine:

    git clone git@github.com:<username>/<repository>.git

    Replace `<username>` with your GitHub username and `<repository>` with your repository name.

### Step 5: Configure GitHub Actions

1. Inside your cloned repository on your local machine, navigate to the root directory of your repository.

2. Create a new directory named `.github` if it doesn't exist:

    mkdir .github


3. Change into the `.github` directory:

    cd .github


4. Create a new directory named `workflows` inside the `.github` directory:

    mkdir workflows


5. Change into the newly created `workflows` directory:

    cd workflows


6. Create a new file with the `.yml` extension (e.g., `deploy.yml`) to define your deployment workflow:

    touch deploy.yml


7. Edit the file and add the desired YAML code, such as the one provided in your previous message, to define your deployment workflow. Customize the script section of the YAML file to match your specific deployment requirements, such as the path to your code and any additional build or configuration steps needed for your application. Save the file.

### Step 6: Push Changes to GitHub

1. Commit and push your changes from your local machine to the GitHub repository.

2. GitHub Actions will automatically trigger the deployment workflow defined in the `deploy.yml` file.

3. Monitor the workflow execution logs in the GitHub Actions tab of your GitHub repository to ensure that the deployment steps are executed successfully.

4. Access your EC2 instance's public IP address in a web browser to verify that the updated code is deployed and visible.

Congratulations! You have successfully set up a CI/CD pipeline using GitHub Actions to deploy changes from your local machine to an EC2 instance running Ubuntu with Nginx.

Feel free to customize the document as per your requirements, adding any additional information or clarifications necessary for your specific setup.