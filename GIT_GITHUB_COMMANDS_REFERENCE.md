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

## 12) Top 15 Daily Shortcuts

- `git st`  
  Common alias for `git status` (if alias configured).

- `git status -sb`  
  Short branch-aware status view.

- `git add -A && git commit -m "message"`  
  Stage everything and commit in one line.

- `git commit -am "message"`  
  Commit tracked file changes in one step (does not include new files).

- `git commit --amend --no-edit`  
  Add latest staged changes to previous commit without changing its message.

- `git commit --amend -m "new message"`  
  Fix previous commit message (and include staged changes if present).

- `git checkout -- <file>`  
  Old shortcut to discard file changes (modern form: `git restore <file>`).

- `git restore .`  
  Discard all unstaged changes in current folder tree.

- `git log --oneline --graph --decorate -n 10`  
  Quick history view with branch pointers.

- `git switch -c feature/<name>`  
  Create and move to a new feature branch in one command.

- `git push -u origin <branch>`  
  First push and set upstream so later `git push` works directly.

- `git pull --rebase`  
  Pull while keeping linear history (replays local commits on top).

- `git fetch --all --prune`  
  Update remote refs and remove stale deleted branches.

- `git branch -d <branch>`  
  Delete merged local branch quickly.

- `git stash -u`  
  Stash tracked and untracked working changes quickly.

## 13) History Search and Inspection

- `git log --oneline --all --decorate --graph`  
  Full branch graph view.

- `git log -- <file>`  
  Show commit history for a specific file.

- `git log -p -- <file>`  
  Show file history with patches.

- `git log --follow -- <file>`  
  Follow file history across renames.

- `git show <commit-hash>`  
  Show details and patch for a commit.

- `git show <commit-hash>:<path/to/file>`  
  Show file content from a past commit.

- `git diff <commit1> <commit2>`  
  Compare two commits.

- `git diff <commit1>..<commit2> -- <file>`  
  Compare one file between two commits.

- `git log -S "text" -- <file>`  
  Find commits where exact text count changed (pickaxe search).

- `git log -G "regex" -- <file>`  
  Find commits where diff lines match a regex pattern.

- `git grep "pattern"`  
  Search current repository content quickly.

- `git shortlog -sn`  
  Contributor commit summary by author.

## 14) Deep Debugging and Root-Cause Commands

- `git blame <file>`  
  Show who last changed each line.

- `git blame -L <start>,<end> <file>`  
  Blame a specific line range only.

- `git bisect start`  
  Start binary search for bug-introducing commit.

- `git bisect bad`  
  Mark current commit as bad.

- `git bisect good <commit-hash>`  
  Mark known good commit.

- `git bisect run <test-command>`  
  Automate bisect with a test command.

- `git bisect reset`  
  Exit bisect and return to original HEAD.

- `git range-diff <base>...<old-branch> <base>...<new-branch>`  
  Compare two versions of a branch series (very useful after rebase).

## 15) History Surgery and Recovery (Advanced)

- `git rebase -i HEAD~<n>`  
  Interactive rebase to squash/reword/reorder recent commits.

- `git rebase --continue`  
  Continue rebase after resolving conflicts.

- `git rebase --abort`  
  Cancel rebase and return to pre-rebase state.

- `git rebase --skip`  
  Skip current patch during rebase.

- `git cherry-pick -x <commit-hash>`  
  Copy a commit and append source hash note.

- `git cherry-pick --continue`  
  Continue cherry-pick after resolving conflicts.

- `git cherry-pick --abort`  
  Abort in-progress cherry-pick.

- `git merge --abort`  
  Abort in-progress merge conflict state.

- `git reset --hard ORIG_HEAD`  
  Return to state before last dangerous operation (when available).

- `git reflog --date=local`  
  View local HEAD movement timeline with timestamps.

- `git fsck --lost-found`  
  Find dangling objects/commits for last-resort recovery.

## 16) Branch, Cleanup, and Multi-Worktree

- `git branch -vv`  
  Show branch tracking and latest commit summary.

- `git branch --merged`  
  List branches already merged into current branch.

- `git branch --no-merged`  
  List branches not yet merged.

- `git fetch --all --prune`  
  Refresh all remotes and remove stale remote refs.

- `git remote prune origin`  
  Remove stale remote-tracking refs for origin.

- `git clean -n`  
  Dry-run untracked file cleanup.

- `git clean -fd`  
  Delete untracked files and directories.

- `git clean -fdx`  
  Delete untracked files including ignored files (careful).

- `git worktree list`  
  List all linked working trees.

- `git worktree add ../repo-hotfix -b hotfix/<name> main`  
  Create separate working tree on new hotfix branch.

- `git worktree remove ../repo-hotfix`  
  Remove linked worktree.

## 17) GitHub CLI: PR, Actions, Releases, and Repo Admin

- `gh pr status`  
  Show your current PR status overview.

- `gh pr checks <pr-number>`  
  Show CI checks for a pull request.

- `gh pr checkout <pr-number>`  
  Check out a PR branch locally.

- `gh pr ready <pr-number>`  
  Mark draft PR as ready for review.

- `gh pr merge <pr-number> --squash --delete-branch`  
  Merge PR with squash and delete branch.

- `gh run list`  
  List GitHub Actions workflow runs.

- `gh run view <run-id>`  
  Show details for one workflow run.

- `gh run watch <run-id>`  
  Stream workflow run progress.

- `gh run rerun <run-id>`  
  Re-run a failed workflow run.

- `gh workflow list`  
  List workflows in repository.

- `gh workflow run "<workflow-name>.yml"`  
  Manually trigger a workflow dispatch.

- `gh release create v1.0.0 --title "v1.0.0" --notes "Release notes"`  
  Create a GitHub Release from a tag.

- `gh release view v1.0.0`  
  View release details.

- `gh release list`  
  List releases.

- `gh repo edit --default-branch main`  
  Set repository default branch.

- `gh repo edit --delete-branch-on-merge`  
  Auto-delete branch after PR merge.

- `gh secret set <NAME>`  
  Create/update repository secret (for Actions, etc.).

---

Tip: In Git, use `--oneline` (not `--online`) with `git log`.
