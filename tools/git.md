# Git

## HEAD

HEAD - leads for the latest commit in the current branch

Detached HEAD - when the head refer to specific commit that not part of specific branch.  
It can happened when we checkout commit that exist in master and in other branch so git doesn't know to which commit in which specific branch we want.

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

delete branch:

```
git branch -D [branch name]
```

## Delete

Delete file from stage area:

```
1. git rm [file name]
2. delete file from the working directory
   git add [deleted file]
```

Revert unstaged changes in tracking files

unstage changes in specific file:

```
1. git checkout [file name]
2. git restore [file name]
```

unstage changes in all trackings files:

```
git checkout .
git restore .
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

undo commit X steps from HEAD

```
git reset --soft HEAD~1
```

1 is the number of steps.

- soft reset - delete commit from the HEAD and keep it on the stage area and working directory
- default reset- delete commit from the HEAD and stage area but not from working directory
- hard reset - delete commit from the HEAD, stage area and working directory
