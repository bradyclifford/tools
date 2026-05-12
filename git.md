# Squash
Squash all changes on a feature branch up to that of `master`.
```
git reset $(git merge-base master yourBranch)
```

### Line Ending Issues
```git rm --cached -r . && git reset --hard```

# Worktrees
I don't use this often but I have used it a handful of times.  When I am having to work on multiple feature branches in the same repo and the same time, it is convenient to have multiple branches checked out at once.  Really, all this does is manages multiple folders with the same repo.

The problem is I don't use it that often so I have to remind myself of the commands:
```
git worktree add -b we-123 ../oe-temp master
..browse to that folder
..make changes
..commit, push
..browse back to original folder
git worktree remove ../oe-temp
```

# Reflog
Have had to use this on occasion when I accidentally delete my commits by a hard reset, or just some who, misplaced some work I thought I committed.

The reflog is like an event stream of commits.
```
git reflog
```

# GC
I have actually never ran this before and realize I should be once in a while on my branches.  It cleans up the repo of file revisions, prunes the reflog and updates stale working trees.
As suggested by the documentation:
> Users are encouraged to run this task on a regular basis within each repository to maintain good disk space utilization and good operating performance.

```
git-gc
```

# Submodules
I am actually not a fan of this method.  It basically lets you add a repo to another repo as a child folder.  I feel it is better to utilize a package manager like nuget or npm to include dependencies into your codebase.

```
git submodule add https://github.com/bradyclifford/myRepo
```

## 🛠 Fixes & Workarounds

### 🔧 Enable faster status with `core.untrackedCache` (if not already)

```bash
git config --global core.untrackedCache true

### If you're on a non-native FS (like WSL or Docker on Mac), try:

```bash
git config --global core.preloadIndex true
```

### As a last resort, rebuild the index:

```bash
rm -f .git/index
git reset
```
