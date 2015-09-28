## Creating a Branch
- A branch is a great way to work on a certain feature or part of the application in a way that will not affect work on other parts of the app.
- When you create a branch, it essentially copies over the state of the current branch you are on. The changes you make will be from this state.

[Documentation for git branch](http://git-scm.com/docs/git-branch)

Creating a new branch:

```
git branch test_branch
```

Switching to that new branch:

```
git checkout test_branch
```

## Merging Branch
- When you want to bring changes from one branch into another you can perform a git merge.
- When a merge is done, Git analyzes the changes between the two states and implements the differences on the main branch.

[Documentation for git merge](http://git-scm.com/docs/git-merge)

Switch to main branch (let's say master):

```
git checkout master
```

Merge changes into master:

```
git merge feature_branch
```

## Git Lab 6
- In this lab we will be practicing branching strategies with Git.
- Here are the steps you will need to follow:
	- Step 1: Create a new project and add a file to it.
	- Step 2: Start a new git repo here.
	- Step 3: Add and commit your changes.
	- Step 4: Create two extra branches - development and test.
	- Step 5: Switch to development and make a change to your project.
	- Step 6: Merge development into test.
	- Step 7: Make a change in test and merge into master.
	- Step 8: Update development to reflect the new changes.

## Delete a Branch

```
git branch -d test_branch
```

## Removing Items from Branch
- In the case that you want to remove files from Git tracking and from the local directory, you will need to remove the files through Git.

[Documentation for git rm](http://git-scm.com/docs/git-rm)

```
git rm "*.txt"
```

```
git commit -m "Remove all text files"
```

## Resetting Stage

```
git reset origin/test.txt
```

```
git checkout -- test.txt
```

## Rebasing