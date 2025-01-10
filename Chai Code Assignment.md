# Welcome to Git and GitHub 

Welcome to Chai Code Cohort's Git and GitHub documentation! This document will guide you on how to use Git & GitHub effectively within Chai & Code Organization This documentation aims to provide a smooth on-boarding experience,  ensure code quality and maintainability by ensuring a standardized workflow
## Introduction to Git & GitHub

### Git
Git is a distributed version control system that tracks changes in source code during software development. Created by Linus Torvalds in 2005, Git has become the standard for version control in modern software development.

It allows multiple developers to work simultaneously on the same project while maintaining a complete history of changes.

Key features of Git:
- **Distributed Development**: Every developer has a complete copy of the repository and they can make changes without any conflicts
- **Branching and Merging**: Create isolated environments for new features using branches and merge them when ready
- **Complete History**: Track who made what changes and when
- **Local Operations**: Work offline with full version control capabilities
- **Data Integrity**: Ensures code changes are tracked accurately
- **Staging Area**: Review and organize changes before committing
- **Fast and Lightweight**: Efficient handling of small and large projects

## GitHub 
GitHub is a web-based hosting service for Git repositories that extends Git's capabilities with collaborative features. It allow us to host git repositories remotely and collaborate with others effectively.

Key features of GitHub:
- Secure, cloud-based storage for your code
-  Collaboration tools like Pull Requests and Issues Tracking
- Project management features
- Code review capabilities
- GitHub Actions for automating workflow

## Why use Git and GitHub?

Git and GitHub allow us to:
1. Track all code changes and maintain history of changes (**Version Control**)
2. Multiple developers can work simultaneously on same project without conflicts (**Collaboration**)
3. Systematic review process through Pull Requests (**Code Review**)
5. Track Issues, Manage Projects, and Milestones (**Project Management**)
6. Provide support for README files and Wiki pages (**Documentation**)

## Installation & Configuration

### Git Installation

To install Git on your system follow these steps:

For windows, go to https://git-scm.com/download/windows and install the setup and follow the installation instructions.

For Mac OS, run following command 
```bash
brew install git
```

In Linux, installation may differ based on your distro
- For Ubuntu based distribution, run following command 
```bash
sudo apt install git  
```
- For arch based distribution
```bash
sudo pacman -S git
```

![[install-git.png]]
### Configuring Git

Set up your Git user name and email using following command:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

![[configure-git.png]]
### GitHub Account Setup

1. Visit https://github.com
2. Click "Sign Up"
3. Choose a username, email, and password
4. Follow the verification process and setup TFA

![[create-github-account.png]]
### SSH Configuration
SSH keys provide secure authentication with GitHub. Here's how to set them up:

1. Generate SSH key:
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```
![[ssh-keygen.png]]
2. Start SSH agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

3. Add SSH key to GitHub:
   - Copy key: `cat ~/.ssh/id_ed25519.pub`
   - Go to GitHub Settings > SSH Keys
   - Click "New SSH Key"
   - Paste your key
![[add-ssh-key-to-github.png]]

## Working with Git & Github
### Cloning Repository

Now that we have installed and configured Git & GitHub, let us start by cloning a repository. You can use `git clone <repo-url>` to clone a repository.

For demonstrating how to clone a repository, I have already initialized and pushed a git repository to GitHub: 

```bash
git clone https://github.com/dhawan-kartik/chai-code-git

cd chai-code-git
```

![[git-clone.png]]
## Basic Git Operations

Some of the common Git commands are as followed:

- `git status` - shows status of repository i.e. staged and unstaged files
  ![[git-status.png]]
- `git add <filename>` - add file to staging area
  ![[git-add-file.png]]
- `git add .` - add all files to staging area
  ![[git-add-all.png]]
- `git commit -m <message>` - commit all staged files with provided message
- `git remote add <name> <url>` - create a connection with a remote repository with provided name and URL
- `git push` - push changes to remote
- `git pull` - pull changes from remote
- `git reset --hard HEAD~1` - reset to previous commit
- `git reset --soft HEAD~1` - soft reset to previous commit keeping changes
- `git log` - show commit history
