## Creating a Branch
- A branch is a great way to work on a certain feature or part of the application in a way that will not affect work on other parts of the app.
- When you create a branch, it essentially copies over the state of the current branch you are on. The changes you make will be from this state.

Creating a new branch:

```
git branch test_branch
```

Switching to that new branch:

```
git checkout test_branch
```

## Removing Items from Branch

```
git rm "*.txt"
```

```
git commit -m "Remove all text files"
```

## Merging Branch

## Delete a Branch

```
git branch -d test_branch
```

## Resetting Stage

```
git reset origin/test.txt
```

```
git checkout -- test.txt
```

## Reverting Changes

## Rebasing