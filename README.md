# Git Merge Request Walkthrough - Complete DevOps Workflow

This project demonstrates a complete Git merge request workflow using two GitHub accounts, simulating real-world DevOps collaboration.

## Project Overview
- **Purpose**: Learn Git collaboration and merge request workflow
- **Accounts Used**: Two GitHub accounts (Account A and Account B)
- **Technologies**: Git, GitHub, Markdown, SSH authentication
- **Outcome**: Successful cross-account merge request with documentation

## Complete Step-by-Step Guide

### PHASE 1: ACCOUNT A SETUP (MAIN REPOSITORY)

#### Step 1: Log into GitHub Account A
1. Open your web browser (Chrome, Firefox, Safari, etc.)
2. Click on the address bar at the top (usually says "Search Google or type URL")
3. Type exactly: github.com then press ENTER key
4. Look for "Sign in" button - it's usually in the top-right corner of the page
5. Click "Sign in" button
6. Type your Account A email address in the first text box
7. Press TAB key to move to password field
8. Type your Account A password
9. Press ENTER key or click "Sign in" button

#### Step 2: Create Main Repository
1. After logging in, look for a + (plus) symbol in the top-right corner of the page
2. Click the + symbol - a dropdown menu will appear
3. In the dropdown menu, click "New repository"
4. You are now on the "Create a new repository" page

**Filling the repository form:**
5. Find the "Repository name" input field
6. Click in the field and type: devops-collaboration-project
7. Press TAB key to move to "Description" field
8. Type: Practice repository for learning Git merge requests with two accounts
9. Make sure "Public" is selected (radio button filled in)
10. **CRITICAL**: Check the box that says "Add a README file"
    - This checkbox is usually under "Initialize this repository with:"
    - Click the empty box to add a checkmark ✓
11. Leave all other options as default
12. Scroll down to find the green "Create repository" button
13. Click "Create repository" button

#### Step 3: Note Your Repository URL
1. After creation, you'll see your repository page
2. Look at the browser address bar - it should show:
   https://github.com/YourAccountAUsername/devops-collaboration-project
3. Copy this URL or keep this tab open - you'll need it later

### PHASE 2: ACCOUNT B SETUP (CONTRIBUTOR)

#### Step 4: Log out of Account A and into Account B
1. In the top-right corner of GitHub, click your profile picture
2. A dropdown menu appears - scroll down and click "Sign out"
3. You'll return to GitHub homepage
4. Click "Sign in" button again
5. Enter your Account B email and password
6. Click "Sign in"

#### Step 5: Fork the Repository
1. In the address bar, type the exact URL from Step 3:
   https://github.com/YourAccountAUsername/devops-collaboration-project
2. Press ENTER
3. You should see the repository you created with Account A
4. Look for the "Fork" button in the top-right corner (it looks like a branching diagram)
5. Click the "Fork" button
6. A popup may appear - select your Account B as the destination
7. Wait for forking to complete - you'll be redirected to your forked copy

#### Step 6: Clone the Forked Repository
1. Open your terminal/command prompt:
   - Windows: Press Windows key + R, type cmd, press ENTER
   - Mac: Press Command + Space, type terminal, press ENTER
   - Linux: Press Ctrl + Alt + T

2. Navigate to where you want to store projects:

   cd ~/Documents

   If Documents doesn't exist, try:
   cd ~/Desktop

3. Clone your forked repository:

   git clone https://github.com/YourAccountBUsername/devops-collaboration-project.git

4. Enter the project directory:

   cd devops-collaboration-project

#### Step 7: Configure Git for Account B

   git config user.name "YourAccountBUsername"
   git config user.email "youraccountb@email.com"

### PHASE 3: MAKING CHANGES

#### Step 8: Create a New Branch

   git checkout -b add-devops-documentation

#### Step 9: Create AWS-SERVICES.md File

Create a file called AWS-SERVICES.md with this content:

# AWS Services Learning Progress

## Services I've Learned:
- **EC2**: Virtual servers in the cloud
- **S3**: Scalable storage service
- **IAM**: Identity and access management
- **VPC**: Virtual private cloud

## Current Project:
Learning Git merge requests for DevOps workflow

## Next Steps:
1. Complete this merge request
2. Practice with AWS CLI
3. Learn Terraform for infrastructure as code

## Command Examples:
- List S3 buckets: aws s3 ls
- Describe EC2 instances: aws ec2 describe-instances

#### Step 10: Verify Your File Was Created

   ls -la
   cat AWS-SERVICES.md

### PHASE 4: GIT COMMANDS

#### Step 11: Stage Your Changes

   git status
   git add AWS-SERVICES.md
   git status

#### Step 12: Commit Your Changes

   git commit -m "Add comprehensive AWS services documentation for DevOps learning"
   git log --oneline -2

#### Step 13: Push to Your Fork

   git push origin add-devops-documentation

### PHASE 5: CREATING PULL REQUEST

#### Step 14: Create Pull Request on GitHub
1. Go back to your web browser (should still be on your Account B fork)
2. Refresh the page if needed (F5 key or reload button)
3. You should see a yellow banner that says:
   "Your recently pushed branches: add-devops-documentation"
4. Click the green "Compare & pull request" button in that banner

OR if you don't see the banner:
5. Click the "Pull requests" tab near the top of the repository page
6. Click the green "New pull request" button
7. Click the "compare across forks" link
8. Ensure:
   - base repository: AccountAUsername/devops-collaboration-project
   - base: main
   - head repository: AccountBUsername/devops-collaboration-project
   - compare: add-devops-documentation

#### Step 15: Fill Out Pull Request Details
1. In "Title" field, type: Add AWS Services Documentation
2. Press TAB to move to description field
3. Type this description:

   Changes Made:
   - Added comprehensive AWS services documentation
   - Included learning progress and next steps
   - Added useful AWS CLI command examples

   Purpose:
   This merge request practices the complete Git workflow for DevOps collaboration.

4. Scroll down to review the "Files changed" tab
5. You should see your AWS-SERVICES.md file with green highlighted additions
6. Scroll back up to the top
7. Click the green "Create pull request" button

### PHASE 6: MERGING (SWITCH BACK TO ACCOUNT A)

#### Step 16: Log out and Back into Account A
1. Click your profile picture → "Sign out"
2. Sign back in as Account A
3. Go to the main repository: https://github.com/YourAccountAUsername/devops-collaboration-project

#### Step 17: Review and Merge
1. Click the "Pull requests" tab
2. You should see your open pull request "Add AWS Services Documentation"
3. Click on the pull request title to open it
4. Review the changes in the "Files changed" tab
5. Go back to the "Conversation" tab
6. Scroll to the bottom of the page
7. Click the green "Merge pull request" button
8. Click "Confirm merge" button
9. You'll see a purple message: "Pull request successfully merged and closed"

#### Step 18: Clean Up
1. You'll see a message: "The add-devops-documentation branch can be safely deleted"
2. Click the "Delete branch" button

### PHASE 7: VERIFICATION

#### Step 19: Verify Merge in Account A Repository
1. You should be on the main repository page
2. Click on the "Code" tab
3. You should see your AWS-SERVICES.md file in the file list
4. Click on AWS-SERVICES.md to view its contents
5. You should see all the content you added

#### Step 20: Update Your Local Repository (Account B)
1. Go back to your terminal
2. Switch to main branch and pull latest changes:

   git checkout main
   git pull https://github.com/YourAccountAUsername/devops-collaboration-project.git main
   ls -la
   cat AWS-SERVICES.md

## Screenshots Documentation

This project includes screenshots documenting the complete workflow in the /screenshots directory.

## Success Indicators

✅ Account A: Repository created with README
✅ Account B: Repository forked successfully
✅ Local: Repository cloned, branch created, file added
✅ Git: Changes committed and pushed
✅ GitHub: Pull request created and merged
✅ Final: File visible in main repository, changes pulled locally

You have now completed a full DevOps collaboration workflow using two GitHub accounts!
