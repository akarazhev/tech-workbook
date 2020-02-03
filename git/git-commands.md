# Git Commands

## Gi clone

Git clone is a command for downloading existing source code from a remote repository (like Github, for example):

```bash
git clone <https://name-of-the-repository-link>
```

## Git branch

We can use the git branch command for creating, listing and deleting branches:

```bash
git branch <branch-name>
```

This command will create a branch locally. To push the new branch into the remote repository, you need to use 
the following command:

```bash
git push -u <remote> <branch-name>
```

Viewing branches:

```bash
git branch or git branch --list
```

Deleting a branch:

```bash
git branch -d <branch-name>
```

## Git checkout

We use git checkout mostly for switching from one branch to another. We can also use it for checking out files and commits:

```bash
git checkout <name-of-your-branch>
```

There is also a shortcut command that allows you to create and switch to a branch at the same time:

```bash
git checkout -b <name-of-your-branch>
```

## Git status

The Git status command gives us all the necessary information about the current branch:

```bash
git status
```

## Git add

We need to use the git add command to include the changes of a file(s) into our next commit. 

To add a single file:

```bash
git add <file>
```

To add everything at once:

```bash
git add -A
```

## Git commit

Git commit is like setting a checkpoint in the development process which you can go back to later if needed. We also 
need to write a short message to explain what we have developed or changed in the source code:

```bash
git commit -m "commit message"
```

## Git push

Git push uploads your commits to the remote repository:

```bash
git push <remote> <branch-name>
```

if your branch is newly created, then you also need to upload the branch with the following command:

```bash
git push --set-upstream <remote> <name-of-your-branch>
```

or 

```bash
git push -u origin <branch_name>
```

## Git pull

The git pull command is used to get updates from the remote repo:

```bash
git pull <remote>
```

## Git revert

A safer way that we can undo our commits is by using git revert. To see our commit history, first we need to use:

```bash
git log -- oneline
```

Then we just need to specify the hash code next to our commit that we would like to undo:

```bash
git revert <hash>
```

## Git merge

When you've completed development in your branch and everything works fine, the final step is merging the branch with 
the parent branch (dev or master).

First you should switch to the dev branch:

```bash
git checkout dev
```

Before merging, you should update your local dev branch:

```bash
git fetch
```

Finally, you can merge your feature branch into dev:

```bash
git merge <branch-name>
```