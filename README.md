# DEPI-git-a2-repo1

## Overview

In this assignment, I demonstrated the process of pushing changes to multiple Git repositories. The task involved the following steps:

1. **Creating three remote repositories** on GitHub.
2. **Cloning one of the repositories** to my local machine.
3. **Making a local change** in the cloned repository.
4. **Pushing the change to three remote repositories** with a single command.

## Steps Taken

### 1. Creating Three Remote Repositories on GitHub

First, I created three new repositories on GitHub to serve as the remote repositories for this task. These repositories are:
- `DEPI-git-a2-repo1`
- `DEPI-git-a2-repo2`
- `DEPI-git-a2-repo3`

I created these repositories directly on GitHub using their web interface.

### 2. Cloning One of the Remote Repositories

Next, I cloned the first repository (`DEPI-git-a2-repo1`) to my local machine using the following Git command:

```bash
git clone git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git
```

This command cloned the `DEPI-git-a2-repo1` repository from GitHub to my local machine.

### 3. Adding Multiple Remote Repositories

After cloning the repository, I needed to add the other two repositories (`DEPI-git-a2-repo2` and `DEPI-git-a2-repo3`) as additional remotes to the local repository.

I checked the existing remote setup using:

```bash
git remote -v
```

This showed that `origin` was pointing to the first repository (`DEPI-git-a2-repo1`).

I then added the second and third repositories as remotes using the following commands:

```bash
git remote add all git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git
git remote set-url --add --push all git@github.com:bakr-mostafa/DEPI-git-a2-repo2.git
git remote set-url --add --push all git@github.com:bakr-mostafa/DEPI-git-a2-repo3.git
```

To confirm the new remotes were added correctly, I ran:

```bash
git remote -v
```

The output confirmed all three repositories were listed under the `all` remote:

```text
all    git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git (fetch)
all    git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git (push)
all    git@github.com:bakr-mostafa/DEPI-git-a2-repo2.git (push)
all    git@github.com:bakr-mostafa/DEPI-git-a2-repo3.git (push)
origin git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git (fetch)
origin git@github.com:bakr-mostafa/DEPI-git-a2-repo1.git (push)
```

### 4. Making Local Changes

I then made a local change by creating a new file called `multi_push.txt`. This file was used to demonstrate pushing changes to multiple repositories. The content was:

```bash
echo "This is a demonstration of pushing to multiple remotes" > multi_push.txt
```

After creating the file, I staged and committed the changes using the following commands:

```bash
git add .
git commit -m "Add multi_push.txt to demonstrate pushing to multiple remotes"
```

### 5. Pushing Changes to Multiple Repositories

Finally, I pushed the commit to all three remote repositories (`DEPI-git-a2-repo1`, `DEPI-git-a2-repo2`, `DEPI-git-a2-repo3`) using the following command:

```bash
git push -f all main
```

This command pushed the changes to all three repositories in one go.

