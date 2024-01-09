# Notes

## GIT STARTED

### What is Git ?

Git was invented by Linus Tolvrads in 2005.

Git is a Version Control System. It keeps track of changes that happen across a set of files.
It  does this by creating a **git-repository** for our project, a hidden directory by the name of **`.git`** where it tracks the changes to the files.

Git takes snapshots (*commits*) of the tracked files, and if and when necessary, we can then travel back in time to any previous version of our files.

#### **Important Terms :**

**Git -** Tracks changes to our files

**Repo -** Tracks the *diffs* (changes) across the codebase.

**Commit -** Snapshot of the tracked files.

**Head -** represents the most recent commit in the current *branch*.

**Branch -** Alternate timeline for our code.

**Merge -** Combine branches into a single codebase.

***

### Git Installation

We check the version of git installed on our system using the following command

```bash
git --version
```

If this command prints a version that is 2 or grater, we're good to go. If not, we'll need to install git on our Operating System.

In order to collaborate, we may need to modify git's configuration. The following command is used to list the configuration

```bash
git config --list
```

git requires us to set our username and email for allowing collaboration. If our name and email aren't already set, we use the following commands.

Command to set username

```bash
git config --global user.name = "User Name"
```

Command to set email

```bash
git config --global user.email = "username@email.com"
```

In git, we can set different usernames and emails, for working on different projects.

Instead of using `--global` flag with the `git config` command, which sets the username and email, at a global level, we can also use `--local` flag. If we set the username and email using it, the provided information will only be used in the current project repository.

***

### `git init`

Command used for creating a **git repository**

```bash
git init
```

Executing this command creates a directory called **`.git`** in the project directory. `.git` is hidden by deault, and is responsible of kepping track of all the changes across the project directory.

To remove git from a project, all we have to do is remove `.git` directory and git is gone.

***

### `git status`

Command to check status of the git repository

```bash
git status
```

It lets us inspect the current state of our repository. It tells us which files are tracked or untracked in the git repository. It also tells us the branch we are currently on, and any changes that have been made to the tracked files in the current branch.

**But, what if there are any files that shouldn't be included in ther repo at all ?**

We may have files that store private keys, or build files, that are unnecessary for the repo. To exclude a file or directory from being tracked by git, we use a `.gitignore` file.

**`.gitignore` :** It is a file that we can place in the repo and we put the path of the files, and directories we want git to ignore.

***

### Staging Area and `git add`

**Staging Area :** Git repositories are like a collection of snapshots(commits) of the project, with the head pointing to the most recent snapshot. But, before taking a snapshot, we have to add the files to the staging area.

Note : Git is like a photographer in a marriage, who takes pictures of everyone that walks onto the satge. Before, For anyone to have thier picture in the Album, they have to be on the stage and then the picture will be clicked.

Being tracked doesn't automatically add the modified files to the staging area. We can manually choose what to stage, and commit. `add` and `reset` commands are used to add and remove files from staging area.

Command to add files to staging area

```bash
git add FILENAME
```

To add all modified files to staging area ot once

```bash
git add .
```

Command to remove one or more files from staging area

```bash
git reset FILENAME
```

Command to reset all files from staging area at once

```bash
git reset .
```

***

### `git commit`

`commit` captures a snapshot of the project's currently staged changes. Commited snapshots are like saved-states or checkpoints of a game, and if and when necessary we can go back in time to any previous commit.

Command to commit staged files into the repo

```bash
git commit -m "made a commit"
```

The `-m` flag adds a message to the commit. The message makes it easier to keep track of the changes made in the commit.

git generates a **unique-id** that identifies every commit in the repo.

Often times, staging the changes and then making a commit is seen as a tedious process. But, there is a shortcut to stage and commit the changes to the branch all in one command. We use the `-a` or `-am` flag with `commit` command for this.

```bash
git commit -am "made a commit"
```

OR

```bash
git commit -a -m "made a commit"
```

We can also check the information about the last few commits using `log` command.

```bash
git log
```

***

## REMOTE

### `git remote`

Git by itself is a very powerful tool. But, over the last decade it has also emerged as the most popular way to collaborate on software projects, because of webistes like [GitHub](https://github.com/), [GitLab](https://about.gitlab.com/), etc. which are development platforms that use git. GitHub is the most popular one.

We can connect local git repository to a `remote` repo on github.

To do this, we create a repository on GitHub first. After this, we get a link to our remote repository.

Command to connect our repo in local machine to a remote repository on GitHub

```bash
git remote add NAME LINK
```

`NAME` is the name we want to give to the remote repo. Typically it is `origin`.
`LINK` is the link to our remote repository.

`git remote` can also be used to see the lsit of all the remote repositories our local repository is connected to.

```bash
git remote
```

We can use `-v` flag to get the link (url) of the remote repository.

```bash
git remote -v
```

We can also get additional information about the remote repository, including branches, etc. using this command

```bash
git remote show origin
```
