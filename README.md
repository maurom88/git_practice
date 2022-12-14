# Git and GitHub practice
This repository contains a series of steps that will teach you a simple workflow for using Git and GitHub.

## Index
1. [Section 1: Create and clone a repository](#section-1-create-and-clone-a-repository)
1. [Section 2: Apply changes locally](#section-2-apply-changes-locally)
1. [Section 3: Push updated repository to GitHub, merge to main/master](#section-3-push-updated-repository-to-github-merge-to-mainmaster)
1. [Section 4: Update your local main/master and keep working](#section-4-update-your-local-mainmaster-and-keep-working)

## Section 1: Create and clone a repository

In this section you will:
1. Create a new remote repository on GitHub
1. Clone the new repository on your computer

Go to https://www.github.com and create a new repository

![New repository menu](./img/001.png)


Enter the required information about your repository.
The only mandatory field is "name", but make sure to check "Add a README file", which will make your life easier later.

![New repository panel](./img/002.png)


In the repository you have just created, click the green button "Code" and copy the https url

![Clone url](./img/003.png)

On your computer, open a command prompt and navigate to the folder where you want to save your local repository (using the `cd` command).
Use `git clone` followed by the url you copied before, to clone the remote repository on your computer.

![Git clone](./img/004.png)

At this point, you will have a folder with the same name as your repository.
Use `cd <folder_name>` to get inside your folder. For example: `cd myRepository`.

![cd folder](./img/006.png)

## Section 2: Apply changes locally

In this section you will:
1. Create a new branch
1. Make some changes
1. Commit the changes you made

Whenever you need to make some changes on a repository, starting from the `main` or `master` branch, you need to create a new branch with the command: `git branch <new_branch_name>`.
Then, switch to the new branch you have just created `git checkout <branch_name>`.

![Create and switch branch](./img/007.png)

As an alternative, you can also combine the two previous commands by using `git checkout -b <new_branch_name>` (this will both create the new branch and switch to it).

Make some changes (for example, I have created a text file called "newFile" in my folder).

![newFile](./img/008.png)

Now that the changes have been saved, you will need to commit them so that Git can register them in its version control system. This is done in two steps:
1. `git add <file_name>` (add to staging environment).
1. `git commit -m "Some message"` (commit the changes).

When `add`ing, you should specify which file(s) to add to the staging environemnt. However, it is also possible to stage all changes at the same time with `git add .` like in the example below:

![Git add and commit](./img/009.png)

## Section 3: Push updated repository to GitHub, merge to main/master

In this section you will:
1. Use `git push` to update a remote repository

Now that everything is updated locally, we can use `git push` to update the repository on GitHub

![New repository panel](./img/010.png)

The only problem is that, even though Git knows which repository to push the contents to (because we cloned it), it doesn't know where to put this specific branch, because it has only been created locally.
Following exactly the instructions in the output message, will solve this issue: `git push --set-upstream origin <branch_name>`

![New repository panel](./img/011.png)

Once `push` has completed uploading the new branch with all its files, let's go back to https://www.github.com and open the repository. A message will say that there is a new branch with recent changes. Click the green button "Compare & pull request"

![Compare and pull request](./img/012.png)

In the following steps, just clicking the green buttons in sequence will allow you to merge the contents from the new branch to main/master.

![Create pull request](./img/013.png)

![Merge](./img/014.png)

At the end, you can decide to delete the new branch, but this will only remove it from GitHub! The local branch, on your computer, will remain intact.

![Merge complete](./img/015.png)

## Section 4: Update your local main/master and keep working

Now, we only need to update our local repository. In your command prompt, first switch back to the main repository with `git checkout main`:

![Checkout main](./img/016.png)

Pull the most recent changes with `git pull`.
This is particularly important when working with other people! If someone else makes changes and merge a branch to main, using `pull` is the only way to have the most updated files on your computer and not risk messing up somebody else's work.

![Git pull](./img/017.png)

## Final comments

If you need to apply more changes, go back to Section 2: Apply changes locally and repeat the procedure until the end
