[[GIT REAL II]]

[[CHAPTER 1: INTERACTIVE REBASE]]

--REBASE (CAN REORDER THE COMMITS, CHANGE COMMENTS, SPLIT/AMEND)
$ git rebase -i HEAD~3 // -i (interactive mode), HEAD~3 (last 3 commits)

> Rebase view:
 - pick: use commit
 - reword: use commit, but edit message
 - edit: use commit, but stop amending (need to use $ git rebase --continue)
 - squash: use commit, but meld into previous commit
 - fixup: like "squash", but discard this commit's log message
 - exec: run command using shell
 
[[CHAPTER 2: STASHING]]

--STASH (WORK IN PROGRESS)
$ git stash save // save in a temp area, allow you to work in another branch
$ git stash apply // retrieve the code saved in temp area
$ git stash list
$ git stash drop // delete the top of saved stash
$ git stash pop // the same of apply -> drop

--CONFLICTS
$ git reset --hard HEAD
$ git stash apply

--STAGING AREA
$ git stash save --keep-index (will not appear on staging area)
$ git stash save --include-untracked (allow untracked files to be stashed)

--SHOW
$ git stash show <stash_name>



