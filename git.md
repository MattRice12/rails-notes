#Branches
  git checkout -b <branch-name>
    --> creates new branch & switch you to that branch-name

  git checkout <branch-name>
    --> switches branches

#Configure a remote for a fork
  https://help.github.com/articles/configuring-a-remote-for-a-fork/

  git remote -v
    --> show all remotes

  git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
    --> adds a remote upstream repository to sync with the fork

#When to Pull
  before you push on your branch, you pull from master (git pull upstream master)
  before you make a new branch, you pull from master

#Pull
  git pull upstream master

#Push
  git push origin <my branch>


#Process:
  1) make a new branch, Pull from master
  2) After making changes, `git pull upstream master`
  3) make a pull request(PR)
  4) After PR is approved, `git pull upstream master`
  5) fix conflicts in code
  6) git add . ---- git commit -m "fixed conflicts"
  7) `git push origin <my branch>`
