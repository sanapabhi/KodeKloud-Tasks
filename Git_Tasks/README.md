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


----------------------------------------------------------------------------------------

# Creating a markdown file containing over 100 advanced Git and GitHub commands, with detailed descriptions and examples.

git_commands_markdown = """
# Advanced Git and GitHub Commands

This document contains over 100 advanced Git and GitHub commands, complete with descriptions and examples for production-level use.

## Git Commands

### Basic Commands

1. **`git init`**
   - Initializes a new Git repository.
   - **Example**: `git init my-repo`

2. **`git clone`**
   - Clones a repository into a new directory.
   - **Example**: `git clone https://github.com/user/repo.git`

3. **`git status`**
   - Shows the working tree status.
   - **Example**: `git status`

4. **`git add`**
   - Adds changes to the staging area.
   - **Example**: `git add .` (adds all changes)

5. **`git commit`**
   - Records changes in the repository.
   - **Example**: `git commit -m "Commit message"`

6. **`git push`**
   - Updates the remote repository with local commits.
   - **Example**: `git push origin main`

7. **`git pull`**
   - Fetches and integrates changes from the remote repository.
   - **Example**: `git pull origin main`

### Branching and Merging

8. **`git branch`**
   - Lists, creates, or deletes branches.
   - **Example**: `git branch new-feature`

9. **`git checkout`**
   - Switches branches or restores working tree files.
   - **Example**: `git checkout new-feature`

10. **`git merge`**
    - Merges changes from one branch into another.
    - **Example**: `git merge new-feature`

11. **`git rebase`**
    - Reapplies commits on top of another base tip.
    - **Example**: `git rebase main`

12. **`git cherry-pick`**
    - Applies the changes from a specific commit.
    - **Example**: `git cherry-pick <commit-hash>`

13. **`git branch -d`**
    - Deletes a specified branch.
    - **Example**: `git branch -d old-feature`

14. **`git checkout -b`**
    - Creates a new branch and switches to it.
    - **Example**: `git checkout -b feature-branch`

### Viewing Changes

15. **`git log`**
    - Shows the commit history.
    - **Example**: `git log --oneline`

16. **`git diff`**
    - Shows changes between commits, commit and working tree, etc.
    - **Example**: `git diff HEAD`

17. **`git show`**
    - Displays information about a specific commit.
    - **Example**: `git show <commit-hash>`

18. **`git blame`**
    - Shows what revision and author last modified each line of a file.
    - **Example**: `git blame file.txt`

19. **`git reflog`**
    - Shows the reference logs for the current branch.
    - **Example**: `git reflog`

### Undoing Changes

20. **`git reset`**
    - Resets the current HEAD to a specified state.
    - **Example**: `git reset --hard <commit-hash>`

21. **`git revert`**
    - Creates a new commit that undoes changes made in a previous commit.
    - **Example**: `git revert <commit-hash>`

22. **`git checkout --`**
    - Discards changes in the working directory.
    - **Example**: `git checkout -- file.txt`

### Stashing Changes

23. **`git stash`**
    - Stashes the changes in the working directory.
    - **Example**: `git stash save "work in progress"`

24. **`git stash pop`**
    - Applies the stashed changes and removes them from the stash.
    - **Example**: `git stash pop`

25. **`git stash list`**
    - Lists all stashed changes.
    - **Example**: `git stash list`

### Remote Repository Management

26. **`git remote`**
    - Manages remote repositories.
    - **Example**: `git remote add origin https://github.com/user/repo.git`

27. **`git remote -v`**
    - Shows remote repository URLs.
    - **Example**: `git remote -v`

28. **`git fetch`**
    - Downloads objects and refs from a remote repository.
    - **Example**: `git fetch origin`

29. **`git push -u`**
    - Sets the upstream branch for the current branch.
    - **Example**: `git push -u origin new-feature`

30. **`git pull --rebase`**
    - Combines fetching and rebasing in a single command.
    - **Example**: `git pull --rebase origin main`

### Advanced Branching

31. **`git branch -m`**
    - Renames the current branch.
    - **Example**: `git branch -m new-name`

32. **`git merge --no-ff`**
    - Merges branches without fast-forwarding.
    - **Example**: `git merge --no-ff feature-branch`

33. **`git rebase -i`**
    - Interactively rebase commits.
    - **Example**: `git rebase -i HEAD~3`

34. **`git reflog expire`**
    - Expires old reflog entries.
    - **Example**: `git reflog expire --expire=now --all`

### Tagging

35. **`git tag`**
    - Lists tags in the repository.
    - **Example**: `git tag`

36. **`git tag -a`**
    - Creates an annotated tag.
    - **Example**: `git tag -a v1.0 -m "Version 1.0"`

37. **`git push origin --tags`**
    - Pushes all tags to the remote repository.
    - **Example**: `git push origin --tags`

### Git Configuration

38. **`git config`**
    - Gets and sets repository or global options.
    - **Example**: `git config --global user.name "Your Name"`

39. **`git config --list`**
    - Lists all configuration settings.
    - **Example**: `git config --list`

### GitHub Specific Commands

40. **`gh repo create`**
    - Creates a new GitHub repository.
    - **Example**: `gh repo create my-new-repo`

41. **`gh repo clone`**
    - Clones a GitHub repository.
    - **Example**: `gh repo clone user/repo`

42. **`gh pr create`**
    - Creates a new pull request.
    - **Example**: `gh pr create --base main --head feature-branch`

43. **`gh pr merge`**
    - Merges a pull request.
    - **Example**: `gh pr merge <PR-number>`

44. **`gh issue create`**
    - Creates a new GitHub issue.
    - **Example**: `gh issue create --title "New Issue" --body "Issue details"`

45. **`gh release create`**
    - Creates a new GitHub release.
    - **Example**: `gh release create v1.0 myfile.zip --title "Release 1.0"`

### Networking and Performance

46. **`git gc`**
    - Cleans up unnecessary files and optimizes the local repository.
    - **Example**: `git gc`

47. **`git fsck`**
    - Verifies the connectivity and validity of objects in the database.
    - **Example**: `git fsck`

48. **`git clean`**
    - Removes untracked files from the working directory.
    - **Example**: `git clean -fd`

### Hooks

49. **`git hooks`**
    - Scripts that run automatically at certain points in the Git workflow.
    - **Example**: Place a script in the `.git/hooks` directory.

### Git Aliases

50. **`git config --global alias.<alias> <command>`**
    - Creates an alias for a Git command.
    - **Example**: `git config --global alias.co checkout` (Now use `git co` instead of `git checkout`)

### Scripting and Automation

51. **`git log --pretty=format:"%h - %an, %ar : %s"`**
    - Customizes the output of `git log`.
    - **Example**: Shows commit hash, author name, date, and commit message.

52. **`git diff --cached`**
    - Shows the staged changes.
    - **Example**: `git diff --cached`

53. **`git blame -L <line_start>,<line_end> <file>`**
    - Blames specific lines in a file.
    - **Example**: `git blame -L 10,20 file.txt`

54. **`git archive`**
    - Creates a tar or zip archive of files from a specific commit.
    - **Example**: `git archive --format=tar HEAD > archive.tar`

### Working with Submodules

55. **`git submodule add`**
    - Adds a new submodule to the repository.
    - **Example**: `git submodule add https://github.com/user/sub
   
    
## Working with Submodules (Continued)

56. **`git submodule init`**
    - Initializes submodules in the repository.
    - **Example**: `git submodule init`

57. **`git submodule update`**
    - Updates the submodules to their latest commits.
    - **Example**: `git submodule update`

58. **`git submodule status`**
    - Displays the current commit checked out in each submodule.
    - **Example**: `git submodule status`

59. **`git submodule deinit`**
    - Deinitializes a submodule.
    - **Example**: `git submodule deinit my-submodule`

## Working with Remotes

60. **`git remote remove <name>`**
    - Removes a remote from the repository.
    - **Example**: `git remote remove origin`

61. **`git remote rename <old-name> <new-name>`**
    - Renames a remote repository.
    - **Example**: `git remote rename origin upstream`

62. **`git push origin :<branch>`**
    - Deletes a branch on the remote repository.
    - **Example**: `git push origin :old-branch`

63. **`git remote prune <name>`**
    - Cleans up stale references to remote branches.
    - **Example**: `git remote prune origin`

## Advanced Log and Diff Options

64. **`git log --graph --oneline --decorate --all`**
    - Visualizes the commit history as a graph.
    - **Example**: `git log --graph --oneline --decorate --all`

65. **`git diff --name-only`**
    - Shows only the names of changed files.
    - **Example**: `git diff --name-only HEAD`

66. **`git log --stat`**
    - Shows the number of insertions and deletions for each commit.
    - **Example**: `git log --stat`

67. **`git diff <commit1> <commit2>`**
    - Shows differences between two commits.
    - **Example**: `git diff HEAD~1 HEAD`

## Handling Conflicts

68. **`git mergetool`**
    - Launches a merge conflict resolution tool.
    - **Example**: `git mergetool`

69. **`git rebase --continue`**
    - Continues the rebase after resolving conflicts.
    - **Example**: After resolving conflicts, run this command.

70. **`git reset --merge`**
    - Resets the index and updates the files in the working tree.
    - **Example**: `git reset --merge`

## Workflow Commands

71. **`git fetch --prune`**
    - Fetches changes from the remote and prunes deleted branches.
    - **Example**: `git fetch --prune`

72. **`git worktree add`**
    - Adds a new working tree linked to a specific commit.
    - **Example**: `git worktree add ../my-feature-branch feature-branch`

## Security and Integrity

73. **`git verify-commit`**
    - Verifies the GPG signature of a commit.
    - **Example**: `git verify-commit <commit-hash>`

74. **`git verify-tag`**
    - Verifies the GPG signature of a tag.
    - **Example**: `git verify-tag v1.0`

## Performance Optimization

75. **`git gc --aggressive`**
    - Runs garbage collection more aggressively.
    - **Example**: `git gc --aggressive`

76. **`git fsck --full`**
    - Checks the integrity of the repository more thoroughly.
    - **Example**: `git fsck --full`

## Configuration and Environment

77. **`git config --global core.editor <editor>`**
    - Sets the default text editor for Git.
    - **Example**: `git config --global core.editor "vim"`

78. **`git config --global merge.tool <tool>`**
    - Sets the default merge tool.
    - **Example**: `git config --global merge.tool meld`

79. **`git config --global user.signingkey <key>`**
    - Sets the GPG key for signing commits.
    - **Example**: `git config --global user.signingkey ABC123`

## Collaboration and Code Review

80. **`gh pr review`**
    - Reviews a pull request with comments.
    - **Example**: `gh pr review --approve`

81. **`gh repo fork`**
    - Forks a repository to your GitHub account.
    - **Example**: `gh repo fork user/repo`

82. **`gh repo sync`**
    - Syncs a forked repository with the upstream repository.
    - **Example**: `gh repo sync`

83. **`gh pr list`**
    - Lists pull requests in a repository.
    - **Example**: `gh pr list`

## Troubleshooting

84. **`git bisect`**
    - Uses binary search to find the commit that introduced a bug.
    - **Example**: `git bisect start`

85. **`git stash apply`**
    - Applies the most recent stashed changes without removing them from the stash.
    - **Example**: `git stash apply`

86. **`git blame -L 10,20 <file>`**
    - Blames lines 10 to 20 in a file.
    - **Example**: `git blame -L 10,20 file.txt`

87. **`git shortlog`**
    - Summarizes commit messages and authors.
    - **Example**: `git shortlog -s -n`

## Repository Management

88. **`git init --bare`**
    - Creates a new bare repository.
    - **Example**: `git init --bare my-bare-repo.git`

89. **`git bundle`**
    - Creates a single file that contains a repository and can be transferred.
    - **Example**: `git bundle create repo.bundle --all`

## Miscellaneous

90. **`git cherry`**
    - Shows commits that are in the current branch but not in the upstream branch.
    - **Example**: `git cherry -v`

91. **`git config --global alias.lg "log --oneline --graph --decorate"`**
    - Creates an alias for a custom log format.
    - **Example**: `git lg`

92. **`git replace`**
    - Replaces an object with another in the repository.
    - **Example**: `git replace <old> <new>`

93. **`git clean -n`**
    - Shows which files would be removed by `git clean`.
    - **Example**: `git clean -n`

## Remote and Fork Management

94. **`git remote show <remote>`**
    - Shows information about a specific remote.
    - **Example**: `git remote show origin`

95. **`git reset HEAD~1`**
    - Resets the current branch to one commit before the latest.
    - **Example**: `git reset HEAD~1`

96. **`git mv <old> <new>`**
    - Moves or renames a file in the repository.
    - **Example**: `git mv oldfile.txt newfile.txt`

97. **`git archive --format=zip HEAD > archive.zip`**
    - Creates a zip archive of the current state of the repository.
    - **Example**: `git archive --format=zip HEAD > archive.zip`

## Creating Custom Scripts

98. **`git alias`**
    - Creates custom commands by defining aliases.
    - **Example**: `git config --global alias.co checkout`

99. **`git flow init`**
    - Initializes a new Git Flow repository.
    - **Example**: `git flow init`

100. **`git checkout -`**
    - Switches to the last checked-out branch.
    - **Example**: `git checkout -`

101. **`git merge --abort`**
    - Aborts a merge process and returns to the pre-merge state.
    - **Example**: `git merge --abort`

## Conclusion

This document contains advanced Git and GitHub commands that can enhance your development workflow. Use these commands to manage your codebase effectively and collaborate efficiently with your team.
"""

# Saving the combined content to a markdown file
git_commands_file_path = '/mnt/data/advanced_git_commands.md'
with open(git_commands_file_path, 'w') as file:
    file.write(git_commands_markdown + additional_git_commands_markdown)

git_commands_file_path
