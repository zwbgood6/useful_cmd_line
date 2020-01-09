# Useful command line

## GitHub command line

**If you push files to master**

step1: Stage the file for commit to your local repository.

`git add .`

step2: Commit the file that you've staged in your local repository.

`git commit -m "update file A"`

step3: Push the changes in your local repository to GitHub.

`git push origin master`

Useful github cml link: https://github.com/joshnh/Git-Commands

**If you push files to a branch named "baseline"**

assume you already have a remote branch named "baseline"

step 1: Clone a remote branch and switch to it

`git checkout -b [branch name] origin/[branch name]`

step 2: Stage the file for commit to your local repository.

`git add .`

step 3: Commit the file that you've staged in your local repository.

`git commit -m "update file A"`

step 4： Push the changes in your local repository to GitHub. 

`git push origin HEAD:<name-of-remote-branch>` (e.g. `git push origin HEAD:baseline`)

## Clone:

If there is no `git clone` button in github repo, i.e.,`https://github.com/tensorflow/models/tree/master/research/efficient-hrl`, we can run

`svn export https://github.com/tensorflow/models/trunk/research/efficient-hrl` (replace `/tree/master` with `/trunk`)

## Build python from source

https://stackoverflow.com/questions/41328451/ssl-module-in-python-is-not-available-when-installing-package-with-pip3

