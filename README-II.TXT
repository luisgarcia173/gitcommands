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

