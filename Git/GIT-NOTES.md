# GIT

## What is version control ?

version control is system that records changes to files over time so that we can track history, collaborate with other and revert to previous version.

##### key point of version control :

1. tracking changes
2. collaboration
3. Revesrion
4. branching
5. merging

##### types of version control :

1. Local version Control
2. Centralized version control (CVCS) - single central server holds all version and users check out files to work on them (e.g SVN)
3. Distrubuted version control (DVCS) - Every user has a complete copy of the repository, allowing for collaboration even without a central server (e.g Git)

##### Benifits :

1. Backup and Restore
2. Collaboration
3. History Tracking
4. Experimentation
5. Audit and Debug

## Git staging and commintig

In git staging and commiting are two key actions thst form the foundation of version control.

#### staging (indexing)

The staging area in Git is a space where changes to your files are prepared before making a commit.

**How it works**
When you modify files in your working directory, those changes are considered "unstaged" until you explicitly add them to the staging area using `git add`
Once a file is added to the staging area, it’s marked for inclusion in the next commit.

**Why it’s useful**

1. **Selectivity**: You can control exactly which changes get committed. For example, if you made several changes to a file, but only want to commit part of it, you can stage specific changes.
2. **Organizing commits**: You can group related changes into a single commit, even if those changes span multiple files.

**common commands for staging:**

1. `git add <file>` : Stages a specific file.
2. `git add .` or `git add --all`: Stages all changes (new, modified, and deleted files) in the current directory.
3. `git add -p` : Interactive mode to stage parts of files (e.g., specific lines or changes).

#### commiting

Once changes have been staged, you can create a commit. A commit in Git represents a snapshot of the project at a specific point in time. It records all the staged changes and adds them to the project’s history.

**How it works:**

1. When you commit, Git takes everything in the staging area and creates a new commit with those changes.
2. Each commit has a unique identifier (SHA hash) and stores information about what changed, when it was changed, and who made the changes (through commit metadata).
3. A commit also includes a commit message that describes the changes, providing context to the project history

**Why it’s important:**

1. **History**: Every commit is a permanent record of the state of the project at that time.
2. **Reversion**: You can revert to any commit in history if needed.
3. **Collaboration**: Commits act as checkpoints that collaborators can refer to when working together.

**Common Commands for Committing:**

1. `git commit` : Commits staged changes.
2. `git commit -m` : "Your commit message": Commits with a message directly in the command.
3. `git commit --amend` : Amends the last commit (e.g., to correct a message or add missed changes).

**The Git Workflow with Staging and Committing:**

1. **Modify files** : You work on your project, and files are created or changed.
2. **Stage changes** : You review the changes and use git add to move specific changes to the staging area.
3. **Commit changes** : Once all the necessary changes are staged, you commit them using git commit, adding a message to describe what the commit includes.

**_Summary_**:

1. **Staging**: (git add) allows you to prepare changes for the next commit.
2. **Committing**: (git commit) saves those staged changes as a new version (or snapshot) in the project’s history.

## Git Branching

**What is a branch?**
A branch in Git is simply a lightweight movable pointer to one of the commits in the repository. The default branch in most Git repositories is called main (formerly master).

1. **Main branch**: Usually the default and most stable branch that contains the official project code.
2. **Feature branches**: Created for working on specific features or changes. Once the feature is complete, the branch can be merged back into the main branch.

**Why Branching is Important?**

1. **Isolated Development**: You can work on new features, bug fixes, or experiments without disturbing the main branch of the code.
2. **Collaboration**: Different team members can work on separate branches and later combine their changes into the main branch.
3. **Parallel Development**: Multiple features can be developed in parallel, each on its own branch.
4. **Safer Workflow**: Changes can be reviewed and tested before merging them into the main branch, preventing issues in the main codebase.

**Types of Branching:**

1. **Feature Branches**: Used to develop new features.
2. **Release Branches**: Used to prepare a new production release.
3. **Hotfix Branches**: Used to quickly patch production issues without disturbing ongoing development in other branches.

**Commands for Branching:**

1. Creating a New Branch:

`git branch <branch_name>`

2. Switching Between Branches:

`git checkout <branch_name>`

3. Creating and Switching to a New Branch:

`git checkout -b <branch_name>
`

4. Listing Branches:

`git branch`

5. Deleting a Branch: Once you no longer need a branch, you can delete it:

`git branch -d <branch_name>`

This deletes the branch locally, but only if the changes have been merged.

If you want to forcefully delete a branch, even if it hasn't been merged, use:

`git branch -D <branch_name>`

**Workflow with Branching:**

1. Start with the Main Branch: Make sure you are on the main branch:

`git checkout main`

2. Create a New Branch for the Feature:

`git checkout -b new-feature`

3. Work on the Feature: You can now make changes and commit them as usual, but all the changes will be isolated to the `new-feature` branch.
4. Switch Back to Main Branch: Once you’re done with the feature or want to check something in the main branch:

`git checkout main`

5. Merge the Feature Branch: After completing and testing the feature, you can merge it back into the main branch:

`git merge new-feature`

6. Delete the Branch: If you no longer need the feature branch, you can delete it:

`git branch -d new-feature`

**Merging Branches**
When you’re done working on a branch, you typically want to merge it into the main branch (or another branch). Git offers multiple ways to merge branches:

**Fast-forward merge**: If the main branch hasn’t changed since you branched off, Git will just move the pointer of the main branch to the most recent commit on your feature branch. No new commits are created.

`git merge new-feature`

**Three-way merge**: If both the main branch and your feature branch have new commits, Git will create a new merge commit that combines the changes from both branches.

`git checkout main`
`git merge new-feature`

**Branching Strategies**

Different teams and projects use different branching strategies, depending on their needs. Here are some common strategies:

**Git Flow:**

1. The project has two main branches: main (for production) and develop (for ongoing development).
2. Feature branches are created from develop and merged back once the feature is complete.
3. Release branches are created from develop to prepare a version for production.
4. Hotfix branches are created from main for emergency bug fixes in production.

**GitHub Flow:**

1. All work happens on the main branch.
2. For each feature, create a new branch from main.
3. Once the feature is complete, open a pull request, have it reviewed, and merge it back into main.

**Trunk-Based Development:**

1. Developers work on short-lived feature branches or directly on the main branch.
2. The goal is to integrate changes frequently and avoid long-lived branches.

**Benefits of Branching:**

1. **Isolated Workspaces**: You can work independently on new features or bug fixes.
2. **Parallel Development**: Multiple people or teams can work on different branches simultaneously.
3. **Safe Testing**: Branches allow you to test and experiment without affecting the main codebase.
4. **Better Collaboration**: Branching helps manage contributions from multiple developers without conflicts.

## Viewing the Commit History

The most basic way to view your project's commit history is using the `git log` command. This shows a list of commits, displaying information like commit hashes, authors, dates, and messages.

Basic Command:

`git log`

This will display a history of commits in reverse chronological order (most recent commit first):

`commit abc1234def5678`
`Author: John Doe <johndoe@example.com>`
`Date:   Tue Sep 21 10:45:32 2024 -0500`

`Add user authentication module`

**Customizing the` git log` Output**
`git log` provides a variety of options for customizing the output to suit your needs.

Show a Specific Number of Commits:
To limit the number of commits shown

`git log -n 5`

**One-Line Summary of Commits:**
For a more concise log, use the --oneline option:
`git log --oneline`

Example Output

`abc1234 Add user authentication module`
`def5678 Fix typo in documentation`
`ghj9012 Update README.md`

**Show Commit History for a Specific File:**
`git log -- <file_name>`

**View Graphical Representation:**

`git log --graph --oneline --all`

**Viewing Changes in Commits**

Sometimes you want to see exactly what changed in a specific commit
Show Differences Between Commits (git diff):

**View changes not yet staged:**
`git diff`

**View changes between commits: To see differences between two commits:**
`git diff <commit1> <commit2>`

**Show what changed in the most recent commit:**

`git log -p -1`

**Viewing Commit Details (git show)**
To see detailed information about a specific commit, including which files were changed and the actual code differences:

`git show <commit_hash>`

**Shortlog for Grouping Commits by Author**

`git shortlog`

**Viewing the Author of Each Line in a File (Blame)**
The `git blame` command is useful for seeing who made changes to each line in a file:

`git blame <file_name>`

**Searching Commit Messages**
If you’re looking for a commit based on a keyword in the commit message, you can search with `git log`:

`git log --grep="<search_term>"`
Ex:
`git log --grep="authentication"`

**Viewing File History (git log for Files)**
To see the history of changes to a specific file:
`git log -- <file_name>`

**Viewing a Specific Commit’s History**
To view the history for a particular commit:
`git log <commit_hash>`

**Viewing the History of Branches**
To view the commit history for all branches in a project:
`git log --all`

**Key Commands:**

1. **git log**: View the entire commit history.
2. **git log** --oneline: View a concise, one-line summary of each commit.
3. **git show** <commit_hash>: Show detailed information about a specific commit.
4. **git diff**: Compare the differences between commits or between the working directory and the repository.
5. **git blame** <file_name>: See who made changes to each line in a file.
6. **git log** -- <file_name>: View the history of changes to a specific file.

## Git Status

The `git status` command is used to display the current state of the working directory and the staging area in Git.

**Changes to Be Committed:**
Files that have been added to the staging area (using `git add`) but not yet committed. These files are ready to be included in the next commit.
Files in this section will be part of the next commit if `git commit` is run.

**Clean Working Directory:**
If there are no changes to track, Git will display a message that the working directory is clean.

**Stage Changes**: When you see changes not staged for commit, you can use git add <file> to stage them for the next commit.

**Unstage Changes**: If a file has been staged and you no longer want to commit it, you can unstage it using:
`git restore --staged <file>`

**Conclusion**
The `git status` command is your go-to tool for checking the state of your working directory and staging area.

## Forking a Repository

Forking refers to creating a personal copy of someone else's repository under your own GitHub account. This is often done when you want to contribute to a project but don’t have write access to the original repository.

**What Is a Fork?**

1. A fork is an exact copy of another repository, but it exists independently under your own account.
2. You can make changes to your fork without affecting the original repository.
3. Forking is commonly used when you want to contribute to a project, especially in open-source communities.

**How to Fork a Repository (GitHub Example):**

1. Navigate to the repository you want to fork on GitHub.
2. Click the "Fork" button in the top-right corner.
3. GitHub will create a copy of the repository under your account.

for fork git repository use command git clone respository name
`git clone <repository name>`

## Making Pull Requests (PR)

A pull request is a mechanism for proposing changes to a repository.
Once you’ve made changes to your forked repository, you can submit a pull request to the original repository to suggest that your changes be merged into the original codebase.

**What Is a Pull Request?**

1. A pull request is a request for the maintainers of the original repository to review your changes and potentially merge them into the main branch.
2. It allows for code review, discussion, and collaboration between developers before changes are accepted.
3. Pull requests provide a way to track and document changes before they are merged.

**Pull Requests**: A method for contributing changes from your fork back to the original repository. It allows for code review and discussion before the changes are merged.

## Branch Management: Merging branches (git merge), resolving conflicts


**pull request  merge**
Merging is the process of combining the work done in different branches into a single branch. Typically, a feature or bug fix is developed in a separate branch, and once it's completed, that branch is merged back into the main development branch
