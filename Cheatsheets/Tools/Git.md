## Basics

- **Initialize Repository**: `git init`
- **Clone Repository**: `git clone <repository_url>`
- **Check Status**: `git status`
- **Add Files to Staging**: `git add <file>` or `git add .` (all files)
- **Commit Changes**: `git commit -m "Commit message"`
- **View Commit History**: `git log`

## Branching and Merging

- **Create New Branch**: `git branch <branch_name>`
- **Switch Branch**: `git checkout <branch_name>`
- **Create and Switch**: `git checkout -b <branch_name>`
- **Merge Branch**: `git merge <branch_name>`
- **Delete Branch (Locally)**: `git branch -d <branch_name>`
- **Delete Branch (Remote)**: `git push origin --delete <branch_name>`

## Remote Repositories

- **Add Remote**: `git remote add origin <repository_url>`
- **Push to Remote**: `git push origin <branch_name>`
- **Pull from Remote**: `git pull origin <branch_name>`
- **Fetch from Remote**: `git fetch origin`

## Undoing Changes

- **Discard Changes in Working Directory**: `git checkout -- <file>`
- **Unstage a File**: `git reset HEAD <file>`
- **Undo Last Commit (Preserve Changes)**: `git reset HEAD~1`
- **Undo Last Commit (Discard Changes)**: `git reset --hard HEAD~1`
- **Revert a Commit**: `git revert <commit_hash>`

## Collaboration

- **Create Pull Request**: (On GitHub/Other Platform)
- **Fetch Remote Changes**: `git fetch origin`
- **Merge Remote Changes**: `git merge origin/<branch_name>`

## Gitignore

- Create a file named `.gitignore` and list files/folders to ignore.

## Configuration

- **Configure User Name**: `git config --global user.name "Your Name"`
- **Configure User Email**: `git config --global user.email "you@example.com"`

## Advanced

- **Interactive Add**: `git add -i` or `git add -p`
- **Stash Changes**: `git stash`
- **Apply Stash**: `git stash apply`
- **Rebase Interactive**: `git rebase -i <commit_hash>`
- **Amend Last Commit**: `git commit --amend`

## Tagging

- **Create Lightweight Tag**: `git tag <tag_name>`
- **Create Annotated Tag**: `git tag -a <tag_name> -m "Tag message"`
- **Push Tags**: `git push origin --tags`

#tools