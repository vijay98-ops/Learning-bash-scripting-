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
```

### When you create a branch (with being on some other branch at the time), then the created branch will be a clone of the current branch you are, at the time of creating the branch. This means, that your new branch will have similar codes and status as the current branch.

### You created this branch and made a commit. Since then, a commit for a bug fix was added to main. This is common with many people working on a codebase simultaneously. You need to update this branch so it has the same commits from main, but you can't just merge that branch into this one. You need that bug fix commit to be in the same order here as it is on main, right after the "drop table" commit. You need to rebase this branch against main to do that. Enter `git rebase main` to rebase this branch. Infact, rebase will rewind the branch to the point where it matched main branch and then add commits from main and then it's own commits on top of it.
