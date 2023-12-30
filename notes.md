# Notes

## GIT STARTED

### What is Git ?

Git was invented by Linus Tolvrads in 2005.

Git is a Version Control System. It keeps track of changes that happen across a set of files.
It  does this by creating a git-repository for our project, a hidden directory by the name of **`.git`** where it tracks the changes to the files.

Git takes snapshots (*commits*) of the tracked files, and if and when necessary, we can then travel back in time to any previous version of our files.

#### **Important Terms :**

**Git -** Tracks changes to our files

**Repo -** Tracks the diffs (changes) across the codebase.

**Commit -** Snapshot of the tracked files.

**Head -** represents the most recent commit in the current *branch*.

**Branch -** Alternate timeline for our code.

**Merge -** Combine branches into a single codebase.

***

### Git Installation

We check the version of git installed on our system usng the following command

```bash
git --version
```

If this command prints a version that is 2 or grater, we're good to go. If not, we'll need to install git on our Operating System.

In order to collaborate, we may need to modify git's configuration. The following command is used to list the configuration

```bash
git config --lsit
```

git requires us to set our username and email for allowing collaboration. If our name and email aren't already set, we use the following commands.

Command to set username

```bash
git config --global user.name = "User Name"
```

Command to set email

```bsh
git config --global user.email = "username@email.com"
```

In git, we can set different usernames and emails, for working on different projects.

Instead of using `--global` flag with the `git comfig` command, which sets the username and email, at a global level, we can also use `--local` flag. If we set the username and email using it, the provided information will only be used in the current project repository.

***

### `git init`

Command used for creating a **git repository**

```bash
git init
```

Executing this command creates a directory called **`.git`** in the project directory. `.git` is hidden by deault, and is responsible of kepping track of all the changes that across the project directory.

To remove git from a project, all we have to do is remove `.git` directory and git is gone.

***
