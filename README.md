# Git Commands CheatSheet (Basic to Advanced)

---

# 1. Basic Git Commands

## Setup & Config
```bash
git config --global user.name "Your Name"          # Set username
git config --global user.email "your@email.com"    # Set email
git config --list                                  # View Git config
```

## Initialize & Clone
```bash
git init                      # Initialize a new Git repo
git clone <repo_url>          # Clone a remote repository
```

## Stage & Commit
```bash
git status                    # Check changes
git add <file>                # Add a file to staging
git add .                     # Add all changes to staging
git commit -m "message"       # Commit staged changes
git commit -am "message"      # Add & commit tracked files (skips `git add`)
```

## Undo Changes
```bash
git restore <file>            # Discard unstaged changes
git restore --staged <file>   # Unstage a file
git commit --amend            # Amend last commit (edit message or changes)
git reset --soft HEAD~1       # Undo last commit, keep changes staged
git reset --hard HEAD~1       # Undo last commit & discard changes (DANGER!)
```

---

# 2. Branching & Merging
```bash
git branch                     # List branches
git branch <branch_name>       # Create a new branch
git checkout <branch_name>     # Switch to branch
git checkout -b <branch_name>  # Create & switch to branch
git merge <branch_name>        # Merge branch into current branch
git rebase <branch_name>       # Rebase current branch onto another
git branch -d <branch_name>    # Delete a branch (safe)
git branch -D <branch_name>    # Force delete a branch (unmerged changes)
```

---

# 3. Remote Repositories
```bash
git remote -v                  # List remote repositories
git remote add origin <url>    # Add a remote repository
git push -u origin main        # Push & set upstream branch
git push                       # Push changes to remote
git pull                       # Pull changes from remote
git fetch                      # Fetch remote changes without merging
```

---

# 4. Advanced Git Commands

## Stashing (Temporary Save)
```bash
git stash                      # Stash changes
git stash list                 # List stashes
git stash apply                # Apply last stash
git stash pop                  # Apply & remove last stash
git stash drop                 # Delete last stash
```

## Log & History
```bash
git log                        # View commit history
git log --oneline              # Compact commit history
git log --graph --decorate     # Visual branch history
git blame <file>               # See who changed each line
```

## Tags (Versioning)
```bash
git tag                        # List tags
git tag v1.0                   # Create a lightweight tag
git tag -a v1.0 -m "message"   # Create annotated tag
git push --tags                # Push tags to remote
```

## Reset & Reflog
```bash
git reset <commit_hash>        # Move HEAD to a commit (keeps changes)
git reset --hard <commit_hash> # Discard all changes up to a commit (DANGER!)
git reflog                     # Show all Git actions (helps recover lost commits)
```

## Submodules
```bash
git submodule add <repo_url>   # Add a submodule
git submodule update --init    # Initialize & update submodules
```

## Cherry-Pick
```bash
git cherry-pick <commit_hash>  # Apply a specific commit to current branch
```

## Rebase Interactive (Squash, Edit Commits)
```bash
git rebase -i HEAD~3           # Interactive rebase (last 3 commits)
```

---

# 5. Git Workflow (Common Commands)
```bash
# Typical workflow:
git pull origin main           # Pull latest changes
git checkout -b feature-branch # Create a feature branch
git add . && git commit -m "msg" # Commit changes
git push origin feature-branch # Push to remote
# Then create a Pull Request (PR) on GitHub/GitLab
```

---

# 6. Git Aliases (Shortcuts)
```bash
git config --global alias.co checkout  # `git co` instead of `git checkout`
git config --global alias.br branch    # `git br` instead of `git branch`
```

---

# 7. Git Diff & Patches
```bash
git diff                      # Show unstaged changes
git diff --staged             # Show staged changes
git diff <commit1> <commit2>  # Compare two commits
git format-patch -1           # Generate patch from last commit
git apply <patch_file>        # Apply a patch
```

---

# 8. Advanced Remote Operations
```bash
git remote prune origin       # Delete stale remote branches
git push origin --delete <branch>  # Delete remote branch
git fetch --all               # Fetch all remotes
```

---

# 9. Git Hooks (Automation)
```bash
# Scripts in `.git/hooks/` (e.g., pre-commit, post-merge)
chmod +x .git/hooks/pre-commit  # Make a hook executable
```

---

# 10. Debugging
```bash
git bisect start              # Binary search to find bug-introducing commit
git bisect good <commit>      # Mark a known good commit
git bisect bad <commit>       # Mark a known bad commit
```

---

# Best Practices
- ✔ Commit small, logical changes.
- ✔ Write clear commit messages.
- ✔ Use branches for features/bugfixes.
- ✔ Pull before pushing to avoid conflicts.
- ✔ Use `.gitignore` for files not to track.

---

 