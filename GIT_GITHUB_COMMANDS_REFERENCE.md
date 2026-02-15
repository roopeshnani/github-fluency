# Git and GitHub Commands Practiced

This file contains the commands we used during your end-to-end Git and GitHub learning path.

## 1) Setup and Configuration

- `git --version`  
  Check installed Git version.

- `git config --global user.name "Your Name"`  
  Set your global Git author name.

- `git config --global user.email "you@example.com"`  
  Set your global Git author email.

- `git config --global init.defaultBranch main`  
  Set default branch name for new repos to `main`.

- `git config --global core.autocrlf true`  
  Normalize line endings in Windows/WSL workflows.

- `git config --global --list`  
  Show global Git configuration.

- `git config --global --get init.defaultBranch`  
  Show current default branch setting.

## 2) Repository Creation and First Commits

- `mkdir github-fluency`  
  Create project folder.

- `cd github-fluency`  
  Move into repo folder.

- `git init`  
  Initialize local Git repository.

- `echo "# GitHub Fluency Repo" > README.md`  
  Create README file.

- `echo "This repo is for learning Git step by step." >> README.md`  
  Append text to README.

- `echo "print('hello git')" > app.py`  
  Create sample Python file.

- `git status`  
  Check file state (untracked/staged/modified).

- `git add README.md`  
  Stage README for next commit.

- `git add app.py`  
  Stage app.py for next commit.

- `git diff`  
  Show unstaged changes.

- `git diff --staged`  
  Show staged changes.

- `git commit -m "..."`  
  Create commit from staged changes.

- `git log --oneline`  
  Show compact commit history.

- `git log --oneline --graph --decorate`  
  Show graph with branch pointers.

- `git log --oneline --graph --decorate --all`  
  Show graph for all branches.

## 3) Branching and Merging

- `git branch`  
  List local branches.

- `git switch -c feature/greeting-update`  
  Create and switch to new feature branch.

- `git switch -c feature/readme-practice`  
  Create PR practice branch.

- `git switch -c practice/undo-recovery`  
  Create undo/recovery practice branch.

- `git switch -c practice/clean-history`  
  Create clean-history branch.

- `git switch -c practice/cherry-target main`  
  Create target branch starting from main.

- `git switch main`  
  Switch back to main branch.

- `git merge feature/greeting-update`  
  Merge feature branch into current branch.

- `git branch -m master main`  
  Rename `master` branch to `main`.

## 4) Remotes and Push/Pull

- `git remote -v`  
  Show configured remotes.

- `git remote add origin <repo-url>`  
  Add remote named origin.

- `git remote set-url origin <repo-url>`  
  Update origin URL.

- `git push -u origin main`  
  Push main and set upstream tracking.

- `git push origin main`  
  Push local main to remote.

- `git pull`  
  Fetch and integrate remote changes.

- `git pull --no-rebase origin main`  
  Pull using merge strategy explicitly.

- `git fetch origin`  
  Download remote updates without merging.

## 5) GitHub CLI and Authentication

- `gh --version`  
  Check GitHub CLI installation.

- `gh auth login`  
  Authenticate GitHub CLI.

- `gh auth status`  
  Show current GitHub CLI auth status.

- `ssh -T git@github.com`  
  Test SSH authentication with GitHub.

- `ls ~/.ssh/*.pub`  
  List available SSH public keys.

- `cat ~/.ssh/id_ed25519.pub`  
  View ed25519 public key.

- `cat ~/.ssh/id_rsa.pub`  
  View RSA public key.

## 6) Repository and PR Workflow with GH CLI

- `gh repo create github-fluency --public --source=. --remote=origin --push`  
  Create GitHub repo from current local folder and push code.

- `gh repo view --web`  
  Open repo in browser.

- `gh pr create --base main --head feature/readme-practice --title "..." --body "..."`  
  Create a pull request.

- `gh pr view --web`  
  Open pull request in browser.

- `gh pr merge --squash --delete-branch`  
  Squash merge PR and delete remote feature branch.

## 7) Collaboration and Conflict Resolution

- `git pull --no-rebase origin main`  
  Bring remote changes and trigger merge when needed.

- `git status`  
  Check conflict state.

- Edit conflict markers in file (`<<<<<<<`, `=======`, `>>>>>>>`) and keep final version.

- `git add README.md`  
  Mark conflict as resolved.

- `git commit -m "Resolve README merge conflict"`  
  Complete merge commit.

- `git push origin main`  
  Push resolved merge.

## 8) Undo and Recovery Commands

- `git restore undo-demo.txt`  
  Discard unstaged changes in file.

- `git restore --staged undo-demo.txt`  
  Unstage file but keep edits in working directory.

- `git revert HEAD --no-edit`  
  Create a safe inverse commit for last commit.

- `git reset --soft HEAD~1`  
  Move HEAD back one commit and keep changes staged.

- `git reset --mixed HEAD~1`  
  Move HEAD back one commit and keep changes unstaged.

- `git stash push -m "wip demo"`  
  Save uncommitted changes temporarily.

- `git stash list`  
  List stashes.

- `git stash pop`  
  Reapply latest stash and drop it from stash list.

- `git rev-parse HEAD`  
  Print current commit hash.

- `git reset --hard HEAD~1`  
  Move back and discard worktree/index changes.

- `git reflog`  
  Show HEAD movement history for recovery.

- `git reset --hard <commit-hash>`  
  Restore repository to a specific commit.

## 9) Clean History Commands

- `git rebase origin/main`  
  Replay local commits on top of latest remote main.

- `git cherry-pick <commit>`  
  Apply a specific commit onto current branch.

- `git reset --soft HEAD~3`  
  Squash workflow helper: collapse several recent commits into one new commit.

## 10) Cleanup and Releases

- `git branch -d feature/readme-practice`  
  Delete local merged feature branch.

- `git tag -a v1.0.0 -m "Release v1.0.0"`  
  Create annotated tag.

- `git push origin v1.0.0`  
  Push tag to GitHub.

## 11) Basic Navigation

- `pwd`  
  Print current directory.

- `cd ~`  
  Go to home directory.

- `cd /`  
  Go to filesystem root directory.

---

Tip: In Git, use `--oneline` (not `--online`) with `git log`.
