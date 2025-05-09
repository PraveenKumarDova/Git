# Top 20 Git & GitHub Scenario-Based Interview Questions and Answers (with Examples)

## 1. Scenario: You accidentally committed sensitive data. How do you remove it?
**Answer:** Use `git filter-branch` or `BFG Repo-Cleaner` to rewrite history and force-push.

**Example:**
```bash
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch secret.txt' --prune-empty --tag-name-filter cat -- --all
git push origin --force --all
```

## 2. Scenario: You need to undo the last commit but keep the changes. What do you do?
**Answer:** Use `git reset --soft HEAD~1` to uncommit but keep changes staged.

**Example:**
```bash
git reset --soft HEAD~1
```

## 3. Scenario: You want to squash multiple commits before merging. How do you do it?
**Answer:** Use interactive rebase to squash commits.

**Example:**
```bash
git rebase -i HEAD~3
```

## 4. Scenario: How do you resolve a merge conflict?
**Answer:** Edit conflicted files, mark conflict resolved, then commit.

**Example:**
```bash
git add <conflicted-file>
git commit
```

## 5. Scenario: You need to clone a repo and switch to a new feature branch. How?
**Answer:** Clone, then checkout a new branch.

**Example:**
```bash
git clone https://github.com/user/repo.git
cd repo
git checkout -b feature-x
```

## 6. Scenario: You made changes on the wrong branch. How do you fix it?
**Answer:** Stash or commit, switch to correct branch, cherry-pick or apply stash.

**Example:**
```bash
git stash
git checkout correct-branch
git stash pop
```

## 7. Scenario: How do you view commit history for a specific file?
**Answer:** Use `git log` with the filename.

**Example:**
```bash
git log -- <file>
```

## 8. Scenario: You want to contribute to an open-source project. What’s the flow?
**Answer:** Fork, clone, create branch, push and create a pull request.

**Example:**
```bash
git clone https://github.com/youruser/project.git
git checkout -b feature
```

## 9. Scenario: You need to tag a release in Git. How do you do it?
**Answer:** Use `git tag` to mark a commit.

**Example:**
```bash
git tag -a v1.0 -m 'Initial release'
git push origin v1.0
```

## 10. Scenario: How do you revert a pushed commit?
**Answer:** Use `git revert` to create a new commit undoing changes.

**Example:**
```bash
git revert <commit-hash>
```

## 11. Scenario: You want to rebase a feature branch with updated main. How?
**Answer:** Switch to feature branch and rebase from main.

**Example:**
```bash
git checkout feature
git rebase main
```

## 12. Scenario: You want to ignore files permanently. How do you do it?
**Answer:** Add file patterns to `.gitignore`.

**Example:**
```bash
echo node_modules/ >> .gitignore
git rm -r --cached node_modules/
```

## 13. Scenario: How do you list all remote branches?
**Answer:** Use `git branch -r` or `git ls-remote`.

**Example:**
```bash
git branch -r
```

## 14. Scenario: You want to push a local branch to a remote repo. How?
**Answer:** Use `git push -u origin <branch>`.

**Example:**
```bash
git push -u origin feature-x
```

## 15. Scenario: You want to remove a file from Git but not from local. How?
**Answer:** Use `git rm --cached`.

**Example:**
```bash
git rm --cached config.json
```

## 16. Scenario: You want to pull code without overwriting local changes. How?
**Answer:** Use `git stash`, pull, then `stash pop`.

**Example:**
```bash
git stash
git pull
git stash pop
```

## 17. Scenario: How do you create a Git alias for a frequent command?
**Answer:** Edit git config to add alias.

**Example:**
```bash
git config --global alias.co checkout
```

## 18. Scenario: You want to see the difference between two branches. How?
**Answer:** Use `git diff branch1..branch2`.

**Example:**
```bash
git diff main..feature
```

## 19. Scenario: You need to clean up local merged branches. How?
**Answer:** Use `git branch --merged` and delete branches.

**Example:**
```bash
git branch --merged | grep -v '\*' | xargs -n 1 git branch -d
```

## 20. Scenario: You want to enforce PR reviews before merging to main. How?
**Answer:** Use GitHub branch protection rules in repo settings.

**Example:**  
Navigate to GitHub > Settings > Branches > Add Rule > Require PR review
