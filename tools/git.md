# Git

## Basic commands

_Check installed Git version_:

```
git --version
```

_Create empty Git repository_:

```
git init
```

_Check working directory and staging area status_:

```
git status
git status -s
```

_Display commits of current branch_:

```
git log
```

_Display files in staging area:_

```
git ls-files
```

_Add files to staging area_:

```
git add [file name]      (add specific file)
git add .                (add all files)
```

_Create commit:_

```
git commit -m "[message]"
```

#

## HEAD

HEAD - leads for the latest commit in the current branch

Detached HEAD - when the head refer to specific commit that not part of specific branch.
It can happened when we checkout commit that exist in master and in other branch so git doesn't know to which commit in which specific branch we want.

_Save changes in Detached HEAD:_

when we have Detached HEAD after staged the changes and committed them we must create new branch to save those changes:

```
git branch [new branch name] [commit number]
```

#

## Branch

_Create new branch:_

```
1. git checkout -b [branch name]
2. git switch -c [branch name]
```

Merge branch to master (from master branch):

```
git merge [branch name]
```

Delete branch:
-d : delete merged branch
-D : force delete branch

```
git branch -D/d [branch name]
```

#

## Delete

_Delete file from stage area:_

```
git rm [file name]
git add [file name]
```

Revert unstaged changes in tracking files:

```
1. git checkout [file name]          (specific file)
   git checkout .                    (all files)

2. git restore [file name]           (same as checkout but new)
   git restore .
```

_Delete unstaged changes in untracking files:_

```
git clean -dn
```

Revert staged changes in tracking files:

1. using reset - reset bring the latest status in the HEAD

```
git reset [file name]
git checkout [file name]
```

2. using restore - same as reset but new

```
git restore --staged [file name]
git checkout [file name]
```

Undo Commit

undo commit X steps from HEAD - 1 is the number of steps.

```
git reset --soft HEAD~1
```

- soft reset - delete commit from the HEAD and keep it on the stage area and working directory
- default reset- delete commit from the HEAD and stage area but not from working directory
- hard reset - delete commit from the HEAD, stage area and working directory
