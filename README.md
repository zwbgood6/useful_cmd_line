# Useful command line

## GitHub command line

step1: Stage the file for commit to your local repository.

`git add .`

step2: Commit the file that you've staged in your local repository.

`git commit -m "update file A"`

step3: Push the changes in your local repository to GitHub.

`git push origin **your-branch**`, i.e. **your-branch** can be **master**

Useful github cml link: https://github.com/joshnh/Git-Commands

## Clone:

If there is no `git clone` button in github repo, i.e.,`https://github.com/tensorflow/models/tree/master/research/efficient-hrl`, we can run

`svn export https://github.com/tensorflow/models/trunk/research/efficient-hrl` (replace `/tree/master` with `/trunk`)

## Build python from source

https://stackoverflow.com/questions/41328451/ssl-module-in-python-is-not-available-when-installing-package-with-pip3

