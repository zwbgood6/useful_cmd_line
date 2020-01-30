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

- no clone button

If there is no `git clone` button in github repo, i.e.,`https://github.com/tensorflow/models/tree/master/research/efficient-hrl`, we can run

`svn export https://github.com/tensorflow/models/trunk/research/efficient-hrl` (replace `/tree/master` with `/trunk`)

- clone a branch

`git clone https://github.com/keyshor/sarl.git -b [branch name] [folder name on your local machine]`

e.g.

`git clone https://github.com/keyshor/sarl.git -b baseline sarl`

## Build python from source

https://stackoverflow.com/questions/41328451/ssl-module-in-python-is-not-available-when-installing-package-with-pip3

## tensorflow

### tensorboard

If we train the code on the server and we want to visualize it locally, then

- from your **local** machine, run

`ssh -N -f -L localhost:16006:localhost:6006 <user@remote>` (e.g. `<user@remote>` can be `wenbo@ash01.seas.upenn.edu`)

- on the **remote** machine, run

`tensorboard --logdir <path> --port 6006` (e.g. `<path>` is where your *checkpoint* files are located)

- on the **local** machine, navigate to http://localhost:16006

**Attention**: 

- If it shows *ERROR: TensorBoard could not bind to port 6006, it was already in use* remotely, then run

`lsof -ti:xxxx | xargs kill -9` (e.g. `xxxx` can be `6006`, it kills the current occupied port)

- When run `tensorboard --logdir <path> --port 6006`, it might show http://ash01:6006/. Do not use this link, **try** http://localhost:16006

**Explanation** of ssh command:

`-N`: no remote commands

`-f`: put ssh in the background

`-L <machine1>:<portA>:<machine2>:<portB>`: forward `<machine2>:<portB>` (remote scope) to `<machine1>:<portA>` (local scope) 


## Python Error

- Assertion error:

Usage: If the cmd does not meet the requirement, it will raise AssertionError. It can be used to debug the code.

e.g.
```
for i, all_steps in enumerate(all_steps_per_key):
        assert len(set(all_steps)) == 1, "For scalar {} the step numbering or count doesn't match. Step count for all runs: {}".format(keys[i], [len(steps) for steps in all_steps])
```

If assert len(set(all_steps)) == 1 is not true, then it will raise

```
AssertionError: For scalar Counters/environment_steps the step numbering or count doesn't match. Step count for all runs: [10000, 10000, 10000, 10000, 10000]
```

- Exception 

Usage: It can also be used to debug the code

e.g.
```
If maze_id == 'Maze':
  a = 1
else:
  raise Exception("Check Maze ID!")
```
