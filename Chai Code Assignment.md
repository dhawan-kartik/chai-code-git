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
![[Pasted image 20250111012723.png]] 
- `git remote add <name> <url>` - create a connection with a remote repository with provided name and URL
![[Pasted image 20250111012930.png]]
- `git push` - push changes to remote
![[Pasted image 20250111012843.png]]  
- `git pull` - pull changes from remote
  ![[Pasted image 20250111012623.png]]
- `git log` - show commit history
  ![[Pasted image 20250111012543.png]]
- `git reset --hard HEAD~1` - reset to previous commit
- `git reset --soft HEAD~1` - soft reset to previous commit keeping changes

```bash
# Check repository status
git status

# Add files to staging
git add <filename>     # Add specific file
git add .             # Add all files

# Commit changes
git commit -m "feat(auth): Add login service"

# Push changes to remote
git push origin <branch-name>

# Pull latest changes
git pull origin <branch-name>

# View commit history
git log

# Reset changes
git reset --hard HEAD~1  # Reset to previous commit
git reset --soft HEAD~1  # Soft reset keeping changes
```

## Commit Conventions

Clear and consistent commit messages are crucial for maintaining a clean project history. In our organization, we follow following syntax for our commit messages.

```
<prefix>(<scope>): <Message>
```

Here`<prefix>` are of following types: 
```
 - `feat` - New feature
 - `fix` - Bug fix
 - `chore` - Maintenance task
 - `refact `- Code refactoring
 - `docs`- Documentation related changes
 - `test` - Add/Modify tests 
```

`<scope>` provides context about what part of the code base is 
affected by this commit. 
```
For eg: 
 - `auth`: authentication related change
 - `api`: change in API
 - `ui:` change related to UI 
 - `migration`: add/updated db migration
 - `db`: database related change
 - `config`: change in configuration 
```

`<Message>` A commit message must be command or instruction to the code base to perform some activity and the first character of first word must be in uppercase and remaining characters must be in lower case.
```
For eg: 
 - feat(auth): Add login service
 - fix(api): Fix 404 in verification mail api
 - chore(payment): remove logs from payment service

NOTE: commits should be small and atomic and must aim to perform a specific task.
```

## Branching Strategy

A consistent branching strategy helps maintain order in the development process. Branches must follow following naming convention:

```
<firstName><initial of lastName>/<scope>/<ticket-id>/<change-summary>
```

Here
- `firstName`: Your first name
- `initial of lastName`: First letter of your last name
- `scope`: Area of change (auth, api, ui, etc.)
- `ticket-id`: Related issue or ticket number
- `change-summary`: Brief description in kebab-case

```
For eg: 
- kartikd/auth/#abc123/implement-login-signup-feature
- rahuls/payment/#xyz789/add-configuration-for-payment-gateway
```

## Pull Request Guidelines

Pull Requests (PRs) are the primary means of contributing code to the project. Title of PR must follow following convention:

```
<Prefix>(<scope>): <Summary of changes>
```

Here, 
- `<prefix>` is same as in commit message but is capitalized
- `<scope>` is enclosed in brackets and define affected module or areas

A PR must have
1. Appropriate prefix (Feat, Fix, etc.)
2. Module/scope in brackets
3. Relevant labels
4. Issue ID reference
5. Description of changes

For example:
```
Feat(auth): Implement OAuth2 authentication

## Changes
- Implemented OAuth2 flow with Google and GitHub
- Added user authentication middleware
- Updated API documentation for auth endpoints
- Added unit tests for auth services

## Issue
Fixes #123
Related to #456

## Type of change
- [x] New feature
- [ ] Bug fix
- [ ] Documentation update
- [ ] Breaking change

## Testing
- [x] Unit tests added
- [x] Integration tests updated
- [x] Manual testing completed

## Screenshots
[If applicable]

## Checklist
- [x] Code follows style guidelines
- [x] Changes tested locally
- [x] Documentation updated
- [x] No new warnings generated
```
## Best Practices

Some of the best practices that you must follow when working with Git & GitHub are: 
#### Regular Commits
- Commit frequently with logical units of change
- Avoid large, monolithic commits
- Keep commits atomic and focused
#### Descriptive Messages
- Write clear, concise commit messages
- Include context when necessary
- Follow commit convention strictly
#### Staying Updated
- Pull changes regularly from main branch
- Resolve conflicts promptly
- Keep local branches up to date
- Use `git fetch` to check for updates without merging
#### Code Review
- Review PRs thoroughly
- Provide constructive feedback
- Address review comments promptly
- Test changes locally before approving

Good Git practices lead to better collaboration, cleaner code, and a more maintainable project. Take time to follow these guidelines, and they will become natural parts of your development workflow.

Thanks.