# Git Introduction

## Setup
- To get setup let's install Git.

## Starting a New Git Repository
- New Git repositories begin by initializing Git in a specific directory.
- This creates a .git file that has information and files to handle the version control process.
- This is normally done when you want to begin adding a project to version control.

[Documentation for git init](http://git-scm.com/docs/git-init)

```
git init
```

## Checking Status
- To view repository status, including your staged changes, you can use this command:

[Documentation for git status](http://git-scm.com/docs/git-status)

```
git status
```

## Adding Files to Staging Area
- When you want to add a file to version control through Git you need to "stage" it first.

[Documentation for git add](http://git-scm.com/docs/git-add)

Add specific file:

```
git add "test.txt"
```

Add all files of a certain type:

```
git add "*.txt"
```

Add all files and directories

```
git add -A
```

## Committing Files
- When you are ready to commit your changes to version control, you perform a Git Commit.
- Commits are only local to your computer, but can be pushed up to a remote server.

[Documentation for git commit](http://git-scm.com/docs/git-commit)

```
git commit -m "Newest changes"
```

## Checking Commit History
- After commits are performed you can get a log of recent commits.

[Documentation for git log](http://git-scm.com/docs/git-log)

```
git log
```

## Diff'ing Commits
- Diff'ing in a way you can examine the differences between files either that have been committed or staged.
- You can take the current state of the repository and compare it to a certain commit or compare it to the HEAD.

[Documentation for git diff](http://git-scm.com/docs/git-diff)

Compare current state to HEAD:

```
git diff HEAD
```

Compare staged files to current repository:

```
git diff --staged
```

## Git Lab 1
- In this lab we will practice the features of Git we have learned so far.
- Here are the steps you will need to follow:
	- Step 1: Create a new folder with a single file.
	- Step 2: Initialize a new Git repository.
	- Step 3: Stage the new file.
	- Step 4: Before committing, check the diff on the new file against the current repository status.
	- Step 5: Commit the file.
	- Step 6: Create a new file, stage it and commit it.
	- Step 7: Check the Git log to see the commit.

## Adding a Remote Repository
- In order to push your changes to a remote repository, you will need to use a server that implements Git over HTTP.
- One of the most common remote repository services is [GitLab](https://gitlab.emboldenmedia.net).
- We will look at how to create a new repository through GitLab and push our existing project.

[Documentation for git remote](http://git-scm.com/docs/git-remote)

## Git Lab 2
- In this lab you will be pushing your project you created in step 1 to GitLab.

## Stashing Changes
- There are some circumstances when you start working on a few files and want to them switch to another branch without creating a new commit.
- Normally, in order to switch to a new branch, the current branch needs to be "clean."
- One option is to stash your changes and come back to them later.

[Documentation for git stash](https://git-scm.com/book/en/v1/Git-Tools-Stashing)

```
git stash
```

- If you need to review your stashed changes you can use this command:

```
git stash list
```

- When you want to reapply your changes you can perform an "apply."
- The below example will apply the most recent stash.

```
git stash apply
```

- You can also apply another stash by name.

```
git stash apply stash@{2}
```

- If you also want to restage any files that were previously staged before the stash, you can use the --index option.

```
git stash apply --index
```

- If you need to remove an applied stash you can use the drop command.

```
git stash drop stash@{2}
```

- If you continue work on the current branch from which you stashed your changes, you may run into trouble when trying to reapply.
- The best option here is to create a branch from the stashed work and merge it into your main branch.

```
git stash branch change_branch
```

## Git Lab 3
- In this lab we will practice stashing with the other principles.
- Here are the steps you will need to follow:
	- Step 1: Create two new files in your project from lab part 2.
	- Step 2: Before committing, stash your changes for both files.
	- Step 3: Reapply your changes from the stash.
	- Step 4: Push your changes to GitLab.

## Reverting Commits
- There definitely comes a time when you need to remove an entire commit from your project history.
- Reverting a commit undoes a single commit based on the hash signature. It does not revert back to the previous state of a project by removing all subsequent commits.
- Creating a reversion takes out an older commit, undoes the changes, and creates a new commit to make the alteration.

[Documentation for git revert](http://git-scm.com/docs/git-revert)

Revert the HEAD:

```
git revert HEAD
```

Revert a specific commit based on its hash:

```
git revert 70460b4b4aece5915caf5c68d12f560a9fe3e4
```

## Resetting Your Repository
- Reverting changes allows you to create a new commit that undoes changes from an old commit. Reset allows you to undo changes in the staging area and local directory.
- There are three main ways you use reset:

[Documentation for git reset](http://git-scm.com/docs/git-reset)

##### Resetting a file: Removes the file from staging, but leaves the working directory unchanged.

```
git reset test.txt
```

##### General reset: Resets the staging area to match the most recent commit and leaves the working directory unchanged.

```
git reset
```

##### Commit reset: Resets the project tip to the commit you specify and leaves the working directory unchanged.

```
git reset 70460b4b4aece5915caf5c68d12f560a9fe3e4
```

- You can optionally choose to alter the current working directory as well by specifying the --hard flag.

```
git reset --hard
```

##Git Lab 4
- In this lab we will practice reverting and resetting.
- Turn to your partner and discuss the difference between reverting and resetting, give an example of when you would use one over the other.  
- Here are the steps you will need to follow:
	- Step 1: Find the hash for the last commit you made in lab 3. 
	- Step 2: Revert that specific commit. 
	- Step 3: Stage a few changes of your choice and reset your working directory.
	- Step 4: Turn to your partner and discuss what step 3's reset just accomplished. 

##Git Lab 5
- In this lab we will be combining several of the principles we learned and you will be asked to research some concepts on your own. 
- Here are the steps you will need to follow:
	- Step 1: Perform a `git clone` of this notes repository.
	- Step 2: Find the folder you just cloned and cd in to it. 
	- Step 3: Create a new file anywhere.
	- Step 4: Stage the changes you made.
	- Step 5: View the respository status.
	- Step 6: Commit your changes.
	- Step 7: Get a log of this commit.
	- Step 8: Add a remote that points to a new repository you set up in your account.
	- Step 9: Push the repo with your changes to this new repository.