# GIT 

## What is version control ?
   version control is system that records changes to files over time so that we can track history, collaborate with other and revert to previous version.

#####  key point of version control : 
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


***Summary***:

1. **Staging**:  (git add) allows you to prepare changes for the next commit.
2. **Committing**:  (git commit) saves those staged changes as a new version (or snapshot) in the project’s history.


## Git Branching 
