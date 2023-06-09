# Managing Multiple Git Repositories: Pushing to Personal and Work Repositories Simultaneously

Table Of Contents

- [Introduction](#Introduction)
- [Prerequisites](#Prerequisites)


## Introduction
In this technical blog post, we will explore the process of setting up Git to push code changes to multiple repositories simultaneously. Specifically, we will focus on pushing changes to both a personal GitHub repository and a work repository. This approach allows developers to maintain separate codebases while easily synchronizing updates between the two repositories.

## Prerequisites
Before getting started, ensure that you have the following prerequisites in place:
- Git installed on your local machine.
- SSH keys set up for your personal GitHub account.
- Access to your personal and work repositories on GitHub.

## Step 1: Setting up SSH for Personal GitHub Account
To push code changes to your personal GitHub repository, you need to set up SSH authentication. Follow these steps:
1. Generate an SSH key pair using the `ssh-keygen` command.
2. Add the generated public key (`id_rsa_personal.pub`) to your personal GitHub account's SSH settings.


## Step 2: Configuring SSH for Personal GitHub Account
To conveniently manage multiple SSH configurations, we will use the SSH config file. Follow these steps:
1. Create or edit the SSH config file located at `~/.ssh/config`.
2. Add the following configuration for your personal GitHub account:


## Step 3: Creating Personal GitHub Repository
To enable synchronization between your personal and work repositories, create a repository with the same name as your work repository on your personal GitHub account. For example, if your work repository is named "arms-data-migration," create a repository with the same name on your personal GitHub account.

## Step 4: Cloning Work Repository and Configuring Git
To set up Git for pushing changes to both repositories, follow these steps:
1. Clone your work repository using the HTTPS [URL]:(git clone https://github.com/YourWorkUsername/arms-data-migration.git)

2. Navigate to the cloned repository: `cd arms-data-migration`.
3. Configure Git remotes to manage multiple repositories:
`
git remote add origin https://github.com/YourWorkUsername/arms-data-migration.git
git remote add personal_origin github.com-personal:/YourPersonalUsername/arms-data-migration.git
git remote add all --add origin --add personal_origin
`

4. Set the URL for pushing to all remotes:
`
git remote set-url --add --push all https://github.com/YourWorkUsername/arms-data-migration.git
git remote set-url --add --push all github.com-personal:/YourPersonalUsername/arms-data-migration.git
`

## Step 5: Pushing Changes to Multiple Repositories
Once everything is set up, you can now push code changes to both your personal and work repositories simultaneously. Use the following command to push changes:

`
git push all
`

## Conclusion
By following this tutorial, you have successfully set up Git to push code changes to both your personal and work repositories at the same time. This approach allows for efficient synchronization between multiple repositories, making it easier to manage and maintain separate codebases. Now you can seamlessly share your work on both your personal GitHub account and work repository, ensuring that updates are reflected in both locations.

Remember to share this newfound knowledge with other developers to help them streamline their Git workflows and improve their productivity. Happy coding!

*Note: Replace "YourWorkUsername" and "YourPersonalUsername" with your actual GitHub usernames in the provided commands.*
