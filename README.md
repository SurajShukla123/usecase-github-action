# usecase-github-action

Use Case: Deploy AWS CloudFormation Stack

**Step 1: Repository Structure**
The GitHub repository should have the following structure:

![image](https://github.com/user-attachments/assets/149ea72f-1694-4c54-a1c3-dae5b2eb3ea9)



.github/workflows/: Contains YAML files for GitHub Actions workflows.
templates/: Stores CloudFormation templates (e.g., example-template.yaml).
README.md: Contains project documentation (optional).


**Step 2: Add Workflow File**
Create a Workflow File:

Navigate to .github/workflows/ and create a file called deploy-cft-stack.yml.
Add the Workflow Code:


**Step 3: Configure Secrets**
Add AWS Credentials to Repository Settings:
Go to Settings > Secrets and variables > Actions in your GitHub repository.
Add the following secrets:
AWS_ACCESS_KEY_ID: Your AWS access key.
AWS_SECRET_ACCESS_KEY: Your AWS secret key.


**Step 4: Add a Sample CloudFormation Template**
Store your CloudFormation template in the templates/ folder. Here’s a simple example (example-template.yaml):



**Step 5: Push Changes to the Repository**
Commit and push all files to your GitHub repository:


git add .github/workflows/deploy-cft-stack.yml templates/example-template.yaml
git commit -m "Add workflow for AWS CloudFormation deployment"
git push origin main



**Step 6: For Manual Trigger the Workflow**

Go to the Actions tab in your GitHub repository.
Select the Deploy AWS CFT Stack workflow.
Click Run Workflow and provide the required inputs:
aws_region: us-east-1
stack_name: my-sample-stack
template_file: templates/example-template.yaml



1. How the Workflow Works
Trigger:

The workflow is triggered on:
Push to the main branch.
Manual trigger via workflow_dispatch.


2. Execution Steps:

Checkout Code: Fetches the repository code.
Configure AWS CLI: Authenticates to AWS using credentials stored in secrets.
Deploy CloudFormation: Executes the AWS Cloudformation deploy command to deploy the stack.\




**Key Notes**
Secrets Management: AWS credentials are stored in GitHub Secrets for security.
Triggering Options: The push event and workflow_dispatch allow automation and manual execution.
Reusable: The workflow can be reused for any stack by modifying input parameters.
