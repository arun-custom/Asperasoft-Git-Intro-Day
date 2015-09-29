# Git Continued

## Git Lab 5
- In this lab we will be combining several of the principles we learned and you will be asked to research some concepts on your own. 
- Here are the steps you will need to follow:
	- Step 1: Perform a `git clone` of this notes repository.
	- Step 2: Find the folder you just cloned and cd in to it. 
	- Step 3: Create a new file anywhere.
	- Step 4: Stage the changes you made.
	- Step 5: View the repository status.
	- Step 6: Commit your changes.
	- Step 7: Get a log of this commit.
	- Step 8: Add a remote that points to a new repository you set up in your GitLab account.
	- Step 9: Push the repo with your changes to this new repository.

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

## Rebasing
- Rebasing allows you to move a branch to a new base commit. That is, taking a branch and making it a new commit at the HEAD of the base branch.
- Rebasing helps the project retain a linear history.

[Atlassian article on rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)

```
git rebase master
```

## Resolving Conflicts
- Conflicts arise when the same content is changed across files.
- This generally occurs when you locally make changes to a branch while simultaneously changing master and then create a merge.
- This can also come about when one developer creates a change and then another developer changes the same lines and tries to perform a pull operation.
- Let's trigger a conflict and see how this can be resolved:
	- Step 1: Create a new file on master.
	- Step 2: Create and commit some changes.
	- Step 3: Switch to a new branch and change the same line as you committed on master.
	- Step 4: Merge your branch into master.
- When a conflict is detected, both pieces of text will remain from each commit:

```
<<<<<<< HEAD
Adding another line
=======
Inserting a line
>>>>>>> test_branch
```

- To fix the branch state, you need to choose which version you want to keep and remove the other pieces of text.
- You can then make a commit as usual.

## Git Lab 7
- In this lab you will work with a partner using GitLab to trigger a conflict and resolve it.
- Here are the steps you will need to follow:
	- Step 1: Create a new repository on your local computer and add a file to it.
	- Step 2: Make some changes to the file and commit those changes.
	- Step 3: Push your changes to GitLab.
	- Step 4: Add your partner's username as a member of your project.
	- Step 5: Have your partner clone the project, make a change, and commit the result.
	- Step 6: Change the same line locally as your partner and commit the result.
	- Step 7: Perform a pull operation - `git pull origin master`
	- Step 8: Fix the conflict and commit and push the result.
	- Step 9: Repeat steps 2 - 9 with a new file so your partner can try fixing the conflict as well.

## Pushing to Remote with SSH
- You also have the option of using SSH to push your repository to GitLab.
- This allows increased security, as your encryption key is generated on your computer and not publicly accessible.
- To use SSH with GitLab you have to first generate a SSH key with a tool called ssh-keygen:

```
ssh-keygen -t rsa -C "name of key"
```

- This command will create a private key and public key to authenticate you with GitLab.
- If you want your ssh keys to automatically be used when authenticating with GitLab, you have to place them in the `~/.ssh` directory.
- Test this out by adding some changes to your last lab and pushing them via SSH.

## Forking
- Forking is the process of creating your own copy of an existing repository so you can work on it.
- This allows you to create your own version of changes, and even submit those changes to the original repository for review by creating a "pull request".
- Forking is only something that occurs through GitHub or GitLab, and is not something you can achieve through the command line.
- Forking is often used as a collaboration tool, because one person can be responsible for taking in pull requests, checking them for issues, and then accepting them.

## Pull Requests
- Pull requests, or merge requests as GitLab calls them, allow developers who are not collaborators (members) to submit changes to the original repository for review.
- This process occurs from a forked repository to the main repository.
- This is one way of collaborating through Git - having one person be responsible for reviewing pull requests and merging them.

## Git Lab 8
- In this lab we will practice forking and submitting pull requests.
- Here are the steps you will need to follow:
	- Step 1: Get into groups of two and select one person to own the main repository (owner).
	- Step 2: Owner should create a new project with a file and push it to GitLab.
	- Step 3: Your coworker should then fork the repository and make a change.
	- Step 4: Coworker should now submit a pull request for the change.
	- Step 5: Owner should accept the pull request and issue a `git pull` to receive the newest changes locally.
	- Step 6: Repeat steps so other partner can be owner.