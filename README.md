# git-github-overview-readme
## What is Git?

Git is a version control system. It allows you to track changes to your code. It also allows you to collaborate with other developers on the same codebase.

## Creating Git and GitHub Repositories

There are a couple ways to get started with Git and GitHub. You can create a new repository on GitHub and clone it to your computer. Or you can create a new repository on your computer and push it to GitHub. You can also fork an existing repository on GitHub and clone it to your computer.

### Create a new repository on GitHub and clone it to your computer

1. Go to [github.com](https://www.github.com/) and sign in to your account.
2. Click the "New" button in the top right corner.
3. Enter a name for your repository.
4. Click the "Create repository" button.
5. Copy the URL of your repository. (ssh if you have an ssh key set up, https otherwise)
6. In your terminal, navigate to the directory where you want to clone your repository.
7. Run `git clone <url>` where `<url>` is the URL of your repository.
8. Run `cd <repo-name>` where `<repo-name>` is the name of your repository.

NOTE: If you cloned from someone else's repository, you will not have permission to push to it. You will need to have the owner of the repository add you as a collaborator. to do this the owner will need to:

1. Go to the repository on GitHub.
2. Click the "Settings" tab.
3. Click "Manage access".
4. Click "Invite a collaborator".
5. Enter the username of the person you want to add as a collaborator.
6. Click "Add <username> to <repo-name>".
7. the person you added will receive an email with a link to accept the invitation.


### Create a new repository on your computer and push it to GitHub

1. In your terminal, navigate to the directory where you want to create your repository.
2. Run `git init` to initialize a new git repository.
3. Run `git add .` to add all files in the current directory to the staging area.
4. Run `git commit -m "Initial commit"` to commit the files in the staging area.
5. Go to [github.com](https://www.github.com/) and sign in to your account.
6. Click the "New" button in the top right corner.
7. Enter a name for your repository.
8. Click the "Create repository" button.
9. Copy the URL of your repository. (ssh if you have an ssh key set up, https otherwise)
10. Run `git remote add origin <url>` where `<url>` is the URL of your repository.
11. Run `git push -u origin master` to push your local repository to GitHub.

### Fork an existing repository on GitHub and clone it to your computer

1. Go to [github.com](https://www.github.com/) and sign in to your account.
2. Go to the repository that you want to fork.
3. Click the "Fork" button in the top right corner.
4. Copy the URL of your repository. (ssh if you have an ssh key set up, https otherwise)
5. In your terminal, navigate to the directory where you want to clone your repository.
6. Run `git clone <url>` where `<url>` is the URL of your repository.
7. Run `cd <repo-name>` where `<repo-name>` is the name of your repository.


## Basic Git Flow

Once you have your Git and GitHub repositories set up, you can start making changes to your code. You can use the following commands to track your changes.  The flow will look something like this:

1.  Run `git pull` to pull the latest changes from the remote repository.
2. Make changes to your code.  Save your changes in vscode.
3. Run `git add .` to add all files in the current directory to the staging area.
4. Run `git commit -m "<message>"` to commit the files in the staging area.
5. Repeat steps 1, 2-4 as necessary.
6. When you are ready to push your changes to GitHub, run `git push origin main`. (this might be `master` instead of `main` depending on your repository)
7. After you push you can tell your collaborators to run `git pull` to pull the latest changes from the remote repository.


### What is the staging area?

The staging area is a place where you can group changes to your code before you commit them.  You can add files to the staging area using `git add <file>`.  This is useful if you want to commit some changes but not others. You can add all files in the current directory to the staging area using `git add .`.  You can remove files from the staging area using `git reset <file>`.  You can remove all files from the staging area using `git reset`.  


### When should I commit?

You should commit your changes whenever you have a working version of your code you want to save. You should also commit your changes whenever you want to save your progress before making a potentially breaking change.  It is also a good idea to commit your changes after you have completed a feature or fixed a bug. 

### When should I push?

You should push your changes to GitHub whenever you want to share your changes with others.  It is also a good idea to push your changes after you have completed a feature or fixed a bug.  As a general rule you should not push broken incomplete code to GitHub, in particular to the main branch.  This is because other people should always be able to pull the main branch and have a working version of the code.

### When should I pull?

You should pull changes from GitHub whenever you want to get the latest version of the code.  You should also pull changes from GitHub whenever you want to get changes that other people have made.  You should pull changes from GitHub before you start working on a new feature or fix a bug.  This is because you want to make sure you are working on the latest version of the code.


## Resolving Merge Conflicts

Sometimes when you pull changes from GitHub you will get a merge conflict.  This happens when you have made changes to the same file as someone else.  You will need to resolve the merge conflict before you can pull the changes from GitHub.  You can resolve the merge conflict by editing the file and removing the merge conflict markers.  Once you have resolved the merge conflict you can commit the changes.  Make sure to talk to the other person who made the conflicting changes to make sure you are both happy with the changes you made.

## Git Commands

Git has a lot of commands. Here are the most important ones:

### git init

This command initializes a new git repository in the current directory.

```
git init
```

### git add

This command adds files to the staging area.  The staging area is a place where you can group changes to your code before you commit them.  This is useful if you want to commit some changes but not others. 


```
// add a single file
git add <file>

// add multiple files
git add <file1> <file2> <file3>

// add all files in the current directory
git add .
```

### git commit

This command commits the files in the staging area.  The message in the commit should describe the changes you made.    

```
git commit -m "message"
```

### git push

This command pushes your local repository to GitHub. The remote is the name of the remote repository. It is usually `origin`, but this is not always the case. The branch is the name of the branch you want to push to. For now this will will be `main` or `master`.  We will talk about branches later.


```
<!-- git push <remote> <branch> -->
// common usage 
git push origin main

// push to the default remote and branch
git push
```

### git pull

This command pulls the latest changes from the remote repository. 

```
<!--  git pull <remote> <branch> -->

// common usage 
git pull origin main

// pull from the default remote and branch
git pull
```
### git clone

This command clones a repository from GitHub to your computer.  The URL is the URL of the repository you want to clone.  The directory is the name of the directory you want to clone the repository to.  If you do not specify a directory, the repository will be cloned to a directory with the same name as the repository.  We do not need to add a remote for the repository we just cloned.

```

// clone a repository to the current directory
git clone <url>

// clone a repository to a specific directory
git clone <url> <directory>
```

### git remote

This command allows you to see, add, and remove remotes. 

```
// list remotes
git remote

// list remotes with more information
git remote -v

// add a remote
<!-- git remote add <remote> <url> -->
git remote add origin <url>

// remove a remote
<!-- git remote rm <remote> -->
git remote rm origin

```





## Vocabulary and Concepts

### version control system

A version control system is a tool that allows you to track changes to your code. It also allows you to collaborate with other developers on the same codebase.

### Why we use Git

We use Git to track changes to our code. It also allows us to collaborate with other developers on the same codebase.

### Github

GitHub is a website that hosts Git repositories. It allows you to collaborate with other developers on the same codebase.

### Git repository

A Git repository is a folder that contains all of the files for a project. It also contains a hidden folder called `.git` that contains all of the information about the project's history.


### Alternative version control systems

There are other version control systems besides Git.  Some of the most popular ones are Mercurial and Subversion.  Git is the most popular version control system.  It is also the most widely used version control system.  It is also the most powerful version control system. 

### Alternatives to GitHub

There are other websites that host Git repositories besides GitHub.  Some of the most popular ones are GitLab and BitBucket.  These are often used in the industry.  

