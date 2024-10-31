# Git: A Comprehensive Guide

Git is a powerful version control system that allows you to track changes in your code over time. Here's a breakdown of essential Git commands, categorized into basic and advanced:

# Basic Git Commands

1. git init: Initializes a new Git repository in the current directory.

        git init


2. git clone: Clones an existing Git repository from a remote source.

        git clone https://github.com/user/repo.git


3. git add: Adds changes to the staging area, preparing them for commit.

        git add filename
        git add .  # Add all changes


4. git commit: Commits changes from the staging area to the local repository.

        git commit -m "Commit message"


5. git status: Shows the current state of the working directory and staging area.

        git status


6. git diff: Shows the difference between commits, files, or the working directory and the staging area.

        git diff filename
        git diff HEAD^ HEAD


7. git log: Shows the commit history.

        git log
        git log --oneline


8. git branch: Manages branches.

        git branch new_branch
        git checkout new_branch
        git branch -d branch_name  # Delete a branch


9. git merge: Merges changes from one branch into another.

        git merge branch_name

10. git push: Pushes local commits to a remote repository.

        git push origin main


11. git pull: Fetches and merges changes from a remote repository.

        git pull origin main

-------------------------------------------------------------------------------------------

# Advanced Git Commands

1. git reset: Resets the current HEAD to a specific state.

        git reset --hard HEAD~1  # Reset to the previous commit


2. git revert: Reverts a specific commit, creating a new commit.

        git revert commit_hash


3. git rebase: Re-applies commits on top of another base commit.

        git rebase main


4. git cherry-pick: Applies specific commits from one branch to another.

        git cherry-pick commit_hash

5. git stash: Temporarily saves changes without committing them.

        git stash
        git stash pop


6. git bisect: Finds the commit that introduced a bug.

        git bisect start
        git bisect good commit_hash
        git bisect bad HEAD


7. git reflog: Shows a log of recent actions, including discarded commits.

        git reflog


8. git config: Configures Git's global or local settings.

        git config --global user.name "Your Name"
        git config --global user.email "your_email@example.com"


● Additional Tips
    
    Use descriptive commit messages.
    Break down large commits into smaller ones.
    Leverage Git's powerful branching and merging features.
    Use Git's interactive rebase for advanced history editing.
    Consider using a Git GUI tool for a visual interface.
