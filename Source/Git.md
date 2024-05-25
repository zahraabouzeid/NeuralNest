## Initializing Repository

```bash
git init
git remote add origin https://github.com/zahraabouzeid/Remote.git
git push --set-upstream origin master
```

## Creating a new Branch

```bash
git checkout -b Branch
git push origin Branch
```

## Stage, commit and push

```bash
git add . 
git commit -m "Commit Message"
git push
```

## Stashing Changes

```bash
git stash save "Stash Name"
git stash list
git stash drop stash@{index}
git stash drop
git stash pop
```

## Reverting uncommitted Changes

```bash
git reset --hard HEAD
```

## Merging

```bash
git checkout master
git pull
git checkout Branch
git merge master
git push
```

## Resolve conflict between branch names
```bash
git branch -m old_branch new_branch
git push origin new_branch
git branch -u origin/new_branch
git checkout old_branch
git revert commit_hash
git push
```

## View remote origin
```bash
git remote show origin
```
## Create a Worktree from a specific Revision
```bash
git worktree add ../directory_name r145157
```

## Reset upstream
```bash
git branch --unset-upstream
git push --set-upstream origin master
```

## Pull a remote Branch
```bash
git fetch
git checkout -b remote-branch origin/remote-branch
git pull
```