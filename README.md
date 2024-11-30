# Practice_30-11-24

1. Set Up Your Repository
Create a Repository:

Log in to GitHub.
Create a new repository or use an existing one.
Clone the repository to your local machine:
bash
Copy code
git clone https://github.com/your-username/your-repo.git
cd your-repo
Initialize the main Branch:

Ensure your main branch is set as the default branch in GitHub:
Go to the Settings tab of your repository.
Under Branches, set main as the default branch.
Create the develop Branch:

Locally create and push a develop branch:
bash
Copy code
git checkout -b develop
git push -u origin develop
Now, your repository has two long-lived branches: main and develop.
2. Work on Features
Create a Feature Branch:

Branch off from develop to start a new feature:
bash
Copy code
git checkout -b feature/add-login develop
Commit changes as you work:
bash
Copy code
git add .
git commit -m "Add login feature"
Push the Feature Branch to GitHub:

bash
Copy code
git push -u origin feature/add-login
Open a Pull Request (PR):

Go to GitHub and navigate to the Pull Requests tab.
Open a PR to merge feature/add-login into develop.
Review and merge the PR when the feature is complete.
Delete the Feature Branch:

Locally and remotely:
bash
Copy code
git branch -d feature/add-login
git push origin --delete feature/add-login
3. Prepare a Release
Create a Release Branch:

Branch off from develop to start a release:
bash
Copy code
git checkout -b release/1.0 develop
git push -u origin release/1.0
Finalize the Release:

Fix bugs or update release-specific configurations.
Commit changes and push:
bash
Copy code
git add .
git commit -m "Finalize release 1.0"
git push
Merge the Release:

Open a PR in GitHub to merge release/1.0 into main.
Open another PR to merge release/1.0 into develop.
Merge both PRs.
Tag the Release:

Tag the main branch for versioning:
bash
Copy code
git checkout main
git tag -a v1.0 -m "Release version 1.0"
git push origin v1.0
Delete the Release Branch:

bash
Copy code
git branch -d release/1.0
git push origin --delete release/1.0
4. Apply Hotfixes
Create a Hotfix Branch:

Branch off from main to fix a production bug:
bash
Copy code
git checkout -b hotfix/fix-login main
git push -u origin hotfix/fix-login
Fix the Issue:

Make the necessary changes, then commit and push:
bash
Copy code
git add .
git commit -m "Fix login bug"
git push
Merge the Hotfix:

Open a PR in GitHub to merge hotfix/fix-login into main.
Open another PR to merge hotfix/fix-login into develop.
Merge both PRs.
Delete the Hotfix Branch:

bash
Copy code
git branch -d hotfix/fix-login
git push origin --delete hotfix/fix-login
Automation with GitHub Actions
To streamline the workflow, you can use GitHub Actions for:
Running automated tests on PRs.
Deploying the main branch to production.
Notifying teams about releases or hotfixes.
Summary of Branching Structure
In your GitHub repository, you'll have the following branches:

Permanent Branches:
main: Stable, production-ready code.
develop: Latest in-progress code.
Temporary Branches:
feature/*: For new features (e.g., feature/add-login).
release/*: For preparing releases (e.g., release/1.0).
hotfix/*: For critical bug fixes (e.g., hotfix/fix-login).
Would you like a GitHub Actions template or help setting this up in your repository?