[[GIT REAL]]

Git [Version Control]
 - DVCS (Distributed Version Control System)
 
Remote Repository Hosting
 Hosted:
  - GitHub
  - BitBucket
 SelfManaged:
  - Gitosis
  - Gitorious
 
[[CHAPTER 1: INTRODUCTION]]

--HELP
$ git help
$ git help <command>

--SETUP
$ git config --global user.name "Luis Garcia"
$ git config --global user.email "luisgarcia173@gmail.com"
$ git config --global color.ui true

--CREATE REPO
$ mkdir <folder>
$ cd <folder>
$ git init

--STATUS [TRACKING]
$ git status

--LOG [TIMELINE]
$ git log

--ADD NEW FILES TO REPO (STAGING)
$ git <file_name>
$ git add . //add everything
$ git add --all //add new and removed files

--COMMIT (SNAPSHOT)
$ git commit -m "Create a README."
$ git commit -a -m "..." //-a skip staging area
$ git commit --amend -m "..." //--amend (add to the last commit), -m (new commit message)

[[CHAPTER 2: STAGING AND REMOTE]]

--DIFF (SHOW UNSTAGED DIFFERENCES SINCE LAST COMMIT)
$ git diff
$ git diff --staged //for staged files

--DISCARD (REFERS TO LAST COMMIT), DON'T DO IT AFTER PUSH
$ git reset HEAD <file _name>
$ git reset --soft HEAD^ //--soft (staging area), HEAD^ (move to commit before HEAD)
$ git reset --hard HEAD^ // undo last commit and all changes
$ git reset --hard HEAD^^ // undo last 2 commits and all changes
$ git checkout -- <file_name> // undo commits

--ADDIND A REMOTE / PUSH TO REPOSITORY
$ git remote add origin <url_address>
$ git remote -v
$ git push -u origin master //origin (remote name), master (local branch)

--SYNC LOCAL REPO (PULL)
$ git pull

--REMOVE REMOTE
$ git remote rm <remote_name>
