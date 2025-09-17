# Create new branch and jump into it.
`git checkout -b Patch1`
# Push new local branch onto remote
`git push -u origin Branch_Name`
# List local branch
`git branch`
# List remote branch
`git branch -r`
# Merge branch
> 1. Switch to the branch you want to merge into
>> `git checkout main`
> 2. Merge the other branch into this one
>> `git merge feature-branch`
> 3. Push the merged result
>> `git push origin main`
# Delete remote branch
`git push origin --delete branch-name`
# Delete local branch
`git branch -D branch-name`

# How to fetch remote branches locally?
`git fetch --all`

---
If you want your local branch to **exactly match the remote branch** (discarding **all** local changes and commits), you can do the following:

```bash
# Make sure you’re on the branch you want to reset
git checkout <branch-name>

# Fetch the latest refs from remote
git fetch origin

# Reset your local branch to match the remote exactly
git reset --hard origin/<branch-name>

# Clean untracked files and directories (optional but often useful)
git clean -fd
```

### Breakdown:

* `git fetch origin` → updates your local knowledge of the remote branch.
* `git reset --hard origin/<branch-name>` → makes your local branch point to the same commit as the remote, discarding **all local commits and changes**.
* `git clean -fd` → removes untracked files and directories (like generated files, temp files).

⚠️ **Warning:** This will permanently erase any uncommitted local changes and commits that aren’t pushed to remote.
