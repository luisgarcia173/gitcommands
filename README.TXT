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
$ git commit -a //merge commit

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
$ git remote -v //-v (verbose output)
$ git push -u origin master //origin (remote name), master (local branch)

--SYNC LOCAL REPO (PULL)
$ git pull

--REMOVE REMOTE
$ git remote rm <remote_name>

[[CHAPTER 3: CLONING AND BRANCHING]]

--CLONE (CREATE A NEW LOCAL REPO WITH THE SAME REMOTE NAME)
$ git clone <remote_name>
$ git clone <remote_name> <new_local_name>

--BRANCH
$ git branch <branch_name> //create
$ git checkout <branch_name> //move the pointer to new branch
$ git checkout -b <branch_name> // create and move to new branch

--MERGE
$ git checkout master
$ git merge <branch_name>

[[CHAPTER 4: COLLABORATION BASICS]]

--PULL
$ git pull //update
$ git fetch //(Sync)

[[CHAPTER 5: BRANCHING]]

--LIST BRANCHES
$ git branch //list local branches
$ git branch  -r // list all remote branches

--REMOTE SHOW
$ git remote show origin // list all branches configured for push/pull

--REMOVING A BRANCH
$ git push origin :<branch_name> //remove remotely
$ git branch -d <branch_name> //locally
$ git branch -D <branch_name> //locally force

--CLEAN REMOVED REFERENCES
$ git remote prune origin

--TAGS
$ git tag //list all tags
$ git checkout <tag_name> 
$ git tag -a <tag_name> -m "..." //add new tag
$ git push --tags



