# DevOps Git Project

This project demonstrates an end-to-end Git workflow for a Junior DevOps Engineer.

## Technologies

- Git
- GitHub
- Linux
- Bash

## Project Structure

- app - Application files
- scripts - Deployment scripts
- config - Configuration files
- docs - Project documentation

## Jenkins CI/CD Pipeline

This project uses Jenkins to automate the CI/CD workflow.

### Pipeline Flow

GitHub
   |
   v
Jenkins
   |
   v
Checkout
   |
   v
Validate
   |
   v
Test
   |
   v
Deploy
   |
   v
Verify
   |
   v
SUCCESS

### Jenkins Stages

1. Checkout - Gets the source code from GitHub
2. Validate - Checks required project files
3. Test - Verifies application files
4. Deploy - Runs the deployment script
5. Verify - Confirms successful deployment

Jenkins is configured to automatically check GitHub for changes using Poll SCM.


