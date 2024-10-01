# Git interview Questions

## Basic Level

#### 1. What is Git, and how does it differ from other version control systems?

Git is a distributed version control system that tracks changes in files and coordinates work among multiple people. Unlike centralized systems, Git allows every developer to have a full copy of the project history on their local machine, enabling offline access and better collaboration.

#### 2. What is the difference between `git init` and `git clone`?

`git init` initializes a new Git repository in an existing project, whereas
`git clone` creates a copy of an existing repository (including all commits and branches) from a remote server to your local machine.

#### 3. How do you stage and commit changes in Git?

Use `git add <file> `to stage changes (add them to the index) and `git commit -m "message"` to commit the staged changes with a descriptive message.

#### 4. What is a branch in Git, and how do you create and switch branches?

A branch is a pointer to a specific commit. To create a new branch, use `git branch <branch-name>`. To switch branches, use `git checkout <branch-name>` or `git switch <branch-name>`.

#### 5. Explain the difference between git pull and git fetch.

`git fetch` downloads changes from the remote repository but does not merge them into your local branch.
`git pull` is a combination of git fetch followed by `git merge`, which incorporates changes into your current branch.

### 6. What is the purpose of git stash, and when would you use it?

`git stash` temporarily saves your working directory’s changes so you can work on something else (e.g., switch branches) without committing the changes. You can later retrieve the stashed changes using `git stash` pop.

#### 7. How can you view the commit history in Git?

Use the `git log` command to view the commit history. You can also format the output with options like `git log --oneline` for a concise view or `git log --graph` for a graphical representation of the commit history.

#### 8. What is a merge conflict, and how do you resolve it?

A merge conflict occurs when two branches modify the same part of a file in different ways. Git cannot automatically resolve these changes. To resolve the conflict, you must manually edit the conflicting file(s), then use `git add` to stage the resolved files and `git commit` to complete the merge.

#### 9. How do you undo the last commit in Git?

Use `git reset --soft HEAD~1` to undo the last commit but keep the changes staged. To undo and unstage the changes, use `git reset --hard HEAD~1`.

#### 10. What is the purpose of a .gitignore file?

A `.gitignore` file specifies which files or directories should not be tracked by Git. This is useful for excluding files like build outputs, local environment configurations, and temporary files.

## Intermediate Level

#### 11. Explain the difference between a "fast-forward" merge and a "three-way" merge.

A `"fast-forward"` merge occurs when the branch being merged has no new commits and the current branch simply moves its pointer forward. A `"three-way"` merge happens when both branches have new commits. Git uses a common ancestor to compare the branches and merge them.

#### 12. What is rebasing in Git, and how is it different from merging?

Rebasing involves moving or combining a sequence of commits to a new base commit. It re-applies your changes on top of another branch, creating a linear history. Merging, on the other hand, creates a merge commit that ties the histories of two branches together without changing the commit history.

#### 13. How do you handle large binary files in Git?

Large binary files can be handled using Git Large File Storage (LFS), which stores references to large files in Git while keeping the actual files in a separate storage.

#### 14. What are Git tags, and how do you create and delete them?

Git tags are used to mark specific points in a repository's history, typically for releases. You can create a tag using `git tag <tag-name>` and delete a tag with `git tag -d <tag-name>`.

#### 15. Can you explain the difference between git reset, git checkout, and git revert?

`git reset` moves the HEAD and optionally modifies the index or working directory.
`git checkout` switches branches or restores working tree files.
`git revert` creates a new commit that undoes changes introduced by previous commits without changing the history.

#### 16. What is the use of git cherry-pick, and when would you apply it?

`git cherry-pick` allows you to apply a specific commit from one branch onto another. It's useful when you want to take specific changes without merging an entire branch.

## Advanced/Pro Level

#### 17. How would you approach squashing commits? Why would you do it?

Squashing combines multiple commits into a single commit using `git rebase -i (interactive rebase)`.
It's useful for cleaning up commit history before merging a feature branch into the main branch, ensuring that the commit history remains concise and meaningful.

#### 18. Explain Git hooks and how they can be used in a project.

Git hooks are scripts that are triggered by Git actions such as committing, pushing, or merging. They can be used to automate tasks like linting, testing, or enforcing commit message guidelines. Hooks are located in the .git/hooks directory.

#### 19. What is the significance of Git workflows like GitFlow, GitHub Flow, and GitLab Flow? Which one do you prefer and why?

These are branching strategies for managing Git projects:
`GitFlow` is more structured with dedicated branches for features, releases, and hotfixes.
`GitHub` Flow focuses on simplicity, using a single main branch and short-lived feature branches.
`GitLab` Flow is similar to GitHub Flow but integrates more closely with deployment pipelines.
Preference depends on team size, project complexity, and release cycles.

#### 20. How do you resolve a detached HEAD state in Git, and what causes it?

A detached HEAD occurs when you check out a commit instead of a branch. You can fix it by creating a new branch with `git checkout -b <new-branch-name>` and continuing work. Otherwise, switching back to a branch will resolve the state.
