Yes 👍 For your SDET journey, keep one complete README.md containing the Git commands you'll actually need as a tester/automation engineer.



Since you're asking for the content to put into your README, use the following.



Git Commands for SDET / QA Automation

\# Git \& GitHub Commands for SDET / QA Automation



This document contains the important Git and GitHub commands used by QA Engineers, Automation Testers, and SDETs.



\---



\# 1. Git Basics



\## Check Git Version



```cmd

git --version

Configure Username

git config --global user.name "Your Name"

Configure Email

git config --global user.email "your-email@example.com"

Check Configuration

git config --global --list

2\. Create / Download Repository

Initialize a Git Repository

git init

Clone a GitHub Repository

git clone https://github.com/USERNAME/REPOSITORY.git

Clone into a Specific Folder

git clone https://github.com/USERNAME/REPOSITORY.git folder-name

Clone a Specific Branch

git clone -b branch-name https://github.com/USERNAME/REPOSITORY.git

3\. Check Repository Information

Check Current Status

git status

Check Remote Repository

git remote -v

Show Remote Details

git remote show origin

Show Git Branches

git branch

Show Remote Branches

git branch -r

Show All Branches

git branch -a

4\. Git Daily Workflow



The most important workflow for an SDET:



Write Automation Code

&#x20;       ↓

Run Tests

&#x20;       ↓

Check Changes

&#x20;       ↓

git status

&#x20;       ↓

git add .

&#x20;       ↓

git commit

&#x20;       ↓

git push

&#x20;       ↓

GitHub



Commands:



git status

git add .

git commit -m "Added login automation tests"

git push origin main

5\. Git Status



Check modified files:



git status



Example:



modified: LoginTest.java

6\. Add Files

Add One File

git add README.md

Add Multiple Files

git add file1.java file2.java

Add a Folder

git add selenium

Add Everything

git add .

7\. Commit

Create Commit

git commit -m "Added login automation tests"

View Commit History

git log

Short Commit History

git log --oneline

Show Last 10 Commits

git log --oneline -10

Graph View

git log --oneline --graph --all

8\. Push

Push Main Branch

git push origin main

Push Current Branch

git push

First Push of New Branch

git push -u origin branch-name



Example:



git push -u origin login-automation

9\. Pull



Pull latest changes from GitHub:



git pull



Or:



git pull origin main



Pull a specific branch:



git pull origin branch-name

10\. Fetch



Fetch remote changes without merging:



git fetch



Fetch from origin:



git fetch origin



Fetch all branches:



git fetch --all



Difference:



git fetch

&#x20;   ↓

Downloads information about remote changes



git pull

&#x20;   ↓

Fetch + Merge



git push

&#x20;   ↓

Local → GitHub

11\. Branches



Branches are very important in real-time projects.



Create Branch

git branch login-automation

List Branches

git branch

Switch Branch

git switch login-automation

Create and Switch

git switch -c login-automation

Old Command for Switching

git checkout login-automation

Switch to Main

git switch main

Delete Local Branch

git branch -d login-automation

Force Delete Local Branch

git branch -D login-automation

12\. Remote Branches

Push New Branch

git push -u origin login-automation

Delete Remote Branch

git push origin --delete login-automation

13\. Merge



Switch to main:



git switch main



Get latest code:



git pull



Merge feature branch:



git merge login-automation



Push:



git push

14\. View Changes

Show Unstaged Changes

git diff

Show Staged Changes

git diff --staged

Show Commit Details

git show commit-id



Example:



git show c24c4af

15\. Undo Changes

Discard Changes in a File

git restore filename



Example:



git restore LoginTest.java



WARNING: This removes uncommitted changes.



16\. Unstage Files



If you accidentally run:



git add .



and want to remove a file from staging:



git restore --staged filename



Example:



git restore --staged LoginTest.java



Your changes remain in the file.



17\. Git Stash



Useful when you are working on one task but need to switch to another task.



Save Current Changes

git stash

View Stashes

git stash list

Apply Latest Stash

git stash apply

Apply and Remove Stash

git stash pop

Delete a Stash

git stash drop

18\. Reset

Unstage Files

git reset

Reset to Previous Commit

git reset --soft HEAD\~1

Mixed Reset

git reset HEAD\~1

Hard Reset

git reset --hard HEAD\~1



WARNING: --hard can permanently remove changes.



Use carefully.



19\. Revert



Create a new commit that reverses an old commit:



git revert commit-id



Example:



git revert c24c4af



git revert is generally safer than git reset when working with shared branches.



20\. Tags



Tags can be used for releases.



Create Tag

git tag v1.0

List Tags

git tag

Push Tag

git push origin v1.0

Push All Tags

git push origin --tags

21\. Git Ignore



Create .gitignore:



notepad .gitignore



Example:



target/

\*.log

.env

.idea/

\*.class

screenshots/

test-output/



Important for automation projects.



Do NOT push:



Passwords

API Keys

Tokens

Database Passwords

.env files containing secrets

Company confidential data

22\. GitHub Remote

Add Remote

git remote add origin https://github.com/USERNAME/REPOSITORY.git

Change Remote URL

git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

Remove Remote

git remote remove origin

Check Remote

git remote -v

23\. Resolve Merge Conflicts



When Git reports a conflict:



<<<<<<< HEAD

Your changes

=======

Other changes

>>>>>>> branch-name



Steps:



Open the conflicted file.

Decide which code to keep.

Remove conflict markers.

Save the file.

Add the file.

git add .

Commit:

git commit -m "Resolved merge conflict"

Push:

git push

24\. Pull Request Workflow



Real-time SDET workflow:



main

&#x20; |

&#x20; ├── login-automation

&#x20; |

&#x20; ├── checkout-automation

&#x20; |

&#x20; └── api-testing



Create branch:



git switch -c login-automation



Write tests.



Run tests.



Check changes:



git status



Add:



git add .



Commit:



git commit -m "Added login automation tests"



Push:



git push -u origin login-automation



Then create a Pull Request on GitHub.



After approval:



git switch main

git pull

25\. Real-Time SDET Git Workflow



Example task:



JIRA Ticket:

AUT-101 - Automate Login Functionality



Create branch:



git switch -c AUT-101-login-automation



Write Selenium tests.



Run tests:



mvn test



Check changes:



git status



Review changes:



git diff



Add:



git add .



Commit:



git commit -m "AUT-101 Added login automation tests"



Push:



git push -u origin AUT-101-login-automation



Create Pull Request.



After merge:



git switch main

git pull origin main



Delete local branch:



git branch -d AUT-101-login-automation

26\. Git + Selenium



Typical automation project:



selenium-automation

│

├── src

│   ├── main

│   └── test

│

├── test-data

├── screenshots

├── reports

├── pom.xml

├── testng.xml

├── .gitignore

└── README.md



Before pushing:



mvn test

git status

git add .

git commit -m "Added Selenium automation tests"

git push

27\. Git + API Testing



Typical API automation project:



api-automation

│

├── src

│   └── test

│

├── postman

├── test-data

├── reports

├── pom.xml

├── .gitignore

└── README.md



Run tests:



mvn test



Then:



git status

git add .

git commit -m "Added API automation tests"

git push

28\. Git + Jenkins



Real-time CI/CD flow:



Developer

&#x20;   ↓

Git

&#x20;   ↓

GitHub

&#x20;   ↓

Jenkins

&#x20;   ↓

Maven

&#x20;   ↓

TestNG

&#x20;   ↓

Selenium / REST Assured

&#x20;   ↓

Test Report



Example:



git add .

git commit -m "Updated automation tests"

git push



Jenkins detects the change and runs the automation suite.



29\. Important SDET Commands



These are the commands you should know very well:



git status

git add .

git commit -m "message"

git push

git pull

git fetch

git clone

git branch

git switch

git switch -c branch-name

git merge

git diff

git log --oneline

git stash

git restore

git revert

git remote -v

30\. Daily Commands — Most Important



For your daily SDET practice:



git status

git add .

git commit -m "Added Selenium login test"

git push



For a new feature:



git switch -c feature-name



After completing it:



git status

git add .

git commit -m "Added feature"

git push -u origin feature-name



After your Pull Request is merged:



git switch main

git pull

git branch -d feature-name

31\. Git Cheat Sheet

git clone       → Download repository

git init        → Create Git repository

git status      → Check changes

git add         → Stage changes

git commit      → Save changes

git push        → Upload to GitHub

git pull        → Download + merge changes

git fetch       → Check/download remote information

git branch      → Manage branches

git switch      → Change branch

git merge       → Combine branches

git diff        → See changes

git log         → See history

git stash       → Temporarily save changes

git restore     → Discard/restore changes

git revert      → Undo a commit safely

git remote -v   → Check GitHub connection

🎯 SDET Learning Priority

Must Know ⭐⭐⭐

git clone

git status

git add

git commit

git push

git pull

git branch

git switch

git merge

git diff

git log

git remote

Should Know ⭐⭐

git fetch

git stash

git restore

git revert

git reset

git tag

Real-Time Team Skills ⭐⭐⭐

Branches

Pull Requests

Merge Conflicts

Code Review

.gitignore

Commit Messages

JIRA → Git Branch → Code → Commit → Push → PR → Merge

🏆 Golden Rule



For your SDET career, remember this workflow:



JIRA Task

&#x20;   ↓

Create Branch

&#x20;   ↓

Write Automation Code

&#x20;   ↓

Run Tests

&#x20;   ↓

git status

&#x20;   ↓

git diff

&#x20;   ↓

git add .

&#x20;   ↓

git commit

&#x20;   ↓

git push

&#x20;   ↓

Pull Request

&#x20;   ↓

Code Review

&#x20;   ↓

Merge

&#x20;   ↓

Jenkins

&#x20;   ↓

Automation Tests



This is the Git knowledge you should build for a real SDET/QA Automation role.

