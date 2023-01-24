### Learning Git by building a **SQL** reference object.

```
$ git log --oneline # for minimal logs
$ git merge feature_branch_name # to bring chenges from temp branch to main
$ git branch -d branch_name
$ git checkout -b branch_name # create new branch and switch to it
$ git stash # to stack your unstaged changes
$ git stash list # to view your stack
$ git stash pop # bring back the changes
$ git stash show # show condensed version of changes in the latest stash list
$ git stash show -p # show full changes of the latest stash
$ git stash show stash@{1} # older than stash@{0}
$ git stash drop stash_name
$ git show # to view the last commit
$ git show HEAD~1 # to view previous commit

#You can add the latest stash while keeping it in the list with git stash apply. Apply your stash with this method.
$ git stash apply

# when git rebase causes conflicts, solve the conflicts manually and then
$ git status
$ git add .
$ git status
$ git rebase --continue

# undo changes or commits
$ git reset HEAD~1
$ git reset HEAD~1 --hard # the changes arenot added to the working tree
$ git reset --soft # the changes are added to the working tree

Reverting is a good way to undo a commit because you don't lose the commit from the history.
$ git revert HEAD
$ git rebase --interactive HEAD~2 # head2 means you have chance to change last two commits
$ git rebase --interactive --root # goto your first commit
```

### When you create a branch (with being on some other branch at the time), then the created branch will be a clone of the current branch you are, at the time of creating the branch. This means, that your new branch will have similar codes and status as the current branch.

### You created this branch and made a commit. Since then, a commit for a bug fix was added to main. This is common with many people working on a codebase simultaneously. You need to update this branch so it has the same commits from main, but you can't just merge that branch into this one. You need that bug fix commit to be in the same order here as it is on main, right after the "drop table" commit. You need to rebase this branch against main to do that. Enter `git rebase main` to rebase this branch. Infact, rebase will rewind the branch to the point where it matched main branch and then add commits from main and then it's own commits on top of it.
