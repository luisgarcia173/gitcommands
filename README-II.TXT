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
$ git stash save "..."
$ git stash apply // retrieve the code saved in temp area
$ git stash list
$ git stash drop // delete the top of saved stash
$ git stash pop // the same of apply -> drop
$ git stash clear // clear stash area

--CONFLICTS
$ git reset --hard HEAD
$ git stash apply

--STAGING AREA
$ git stash save --keep-index (will not appear on staging area)
$ git stash save --include-untracked (allow untracked files to be stashed)

--SHOW
$ git stash list --stat
$ git stash show <stash_name>
$ git stash show <stash_name> --patch

--BRANCHING
$ git stash branch <branch_name> <stash_name> //should create a branch from stash
$ git commit -am "..."

[[CHAPTER 3: PURGING HISTORY]]

> Should use only when commited files violate someone's copyright or large binary files, because it removes the commits history.

--TREE FILTER (CHANGE->RECOMMIT)
$ git filter-branch --tree-filter <shell_command>
 -> --tree-filter 'rm -f passwords.txt' (for instance: bad files)
 -> --tree-filter 'find . -name "*.mp4" -exec rm {} \;' (for instance: find/remove videos)
$ git filter-branch --tree-filter <shell_command> -- --all (Exec the same cmd to all commits)
$ git filter-branch -f --tree-filter <shell_command> //force

--INDEX FILTER (CHANGE ON STAGING AREA)
$ git filter-branch --index-filter <shell_command>
 -> --index-filter 'git rm --cached --ignore-unmatch passwords.txt'
 
--PRUNE EMPTY COMMITS
$ git filter-branch -f --prune-empty -- --all

[[CHAPTER 4: WORK TOGETHER]]

--LINE ENDING
$ git config --global core.autocrlf input (Linux based)
$ git config --global core.autocrlf true (Windows based)
$ git config core.autocrlf false (Only Windows)

--GIT ATTRIBUTES
> Should use .gitattributes (file)
 - *			text=auto
 - *.html		text
 - *.css		text
 - *.bat		text eol=crlf
 - *.sh			text eol=lf
 - *.jpg		binary

--CHERRY-PICK (USE SPECIFIC COMMIT IN ANOTHER BRANCH)
$ git checkout <branch_name>
$ git cherry-pick <sha_hash>

--CHERRY-PICK EDIT COMMIT
$ git cherry-pick --edit <sha_hash> (will be opened a popup to edit the comment)

--CHERRY-PICK CUSTOMIZE COMMIT
$ git cherry-pick --no-commit <sha_hash1> <sha_hash2> (combine two commits in one and add to staging area)

--CHERRY-PICK TRACKING
$ git cherry-pick -x <sha_hash> (add source hash to commit msg)

--CHERRY-PICK SIGNING OFF
$ git cherry-pick -signoff <sha_hash> (add source commiter to commit msg)
 
[[CHAPTER 5: SUBMODULES]]

[[CHAPTER 6: REFLOG]]

