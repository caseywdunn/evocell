# Version control with Git

## Reading
>Haddock, SHD and CW Dunn, "Version Control" - unpublished chapter draft, to be distributed in class

## Getting started

Install git:

- MacOSX: In your terminal, type `git --version`. If you don't have git, you will be prompted to install Xcode.  Alternatively, download git [here](https://git-scm.com) . Note: you may need to update a previously installed version of Xcode (App Store), especially if you updated your OS since you installed Xcode.

- Windows: [git](https://git-scm.com)

Make a [github](https://github.com/) account, if you haven't already.

## Git

Git is one of the most widely used version control systems. Today we will be using [github](https://github.com/), but another free git-based hosting system is [Bitbucket](https://bitbucket.org/)

### Install & configure git

!!! Replace "Your name" with your name. "your@email.address" should be the email address associated with your GitHub account.
```
git config --global color.ui "auto"
git config --global user.name "Your name"
git config --global user.email "your@email.address"
<!-- git config --global core.editor emacs -->
```
## Key git commands

`git commit` - this is a snapshot of your latest changes. You use commit to save a snapshot of the files you are editing, add files, and delete files within your repository. Commit often, as you can go back in your version history.
e.g `git commit -am "fixed typo"`

`git push` - once you have made a commit, you can use `git push` to push the changes made locally to your online repo (such as Github).

`git pull` - you can use `git pull` to pull changes made by you or others that are on the online repo.

`git status` - check the status of your repo. Do you have any changes that aren't committed?

`git add` - add a file to your repository

Git works well with text files (containing your R scripts, for example), but you can upload any other type of file. Large files are not supported.

## Setting up a git repository

### From your computer

Create a folder called `scripts` (`mkdir scripts`) that will become your repository. It's up to you where you put it, but I like to keep all my Git repositories in a folder called `Git`.

`cd scripts`
Using Atom create a file called `README.md`. You could type something like "This is a repository containing scripts from my EvoCell workshop". Save it in scripts.

```
git init
git add README.md
git commit -am "Added a readme"
git push
```

You should get a warning like this:
```
fatal: No configured push destination.
Either specify the URL from the command-line or configure a remote repository using

    git remote add <name> <url>

and then push using the remote name

    git push <name>
```
You need to connect your github account to this local repo.

Now go to Github. Click "New Repository" - give it the same name `scripts`.

Follow the instructions for "…or push an existing repository from the command line"
```
git remote add origin https://github.com/[your username]/scripts.git
git push -u origin master
```

It will ask for your password - this is the password you used to set up your github account.

Now check the status using `git status`

You just made your first repo!!

## Git Ignore

The file `.gitignore` is incredibly useful. You can open it up in your terminal using `nano`, `vi`, `vim` or your favourite text viewer/editor.

`nano .gitignore`

Write in the names of any files that you don't want to add or track in your repo. This could include, for example, very very large data files that you use locally or on a server/cluster.

## Cloning an existing repository

You can also set up a local repo that is based on code in an existing repo. For example, the evocell course has a git repo! On Monday, you cloned this repo into your docker container.

`git clone https://github.com/cmunro/evocell.git`

This creates a local folder of this git repo. If you had write access, you could `push` to this repo too.

## Markdown

You will notice that all the readme files have the extension `.md`. These are Markdown files - and it uses a very simple syntax for text formatting. Open up any of the files in the `exercises` folder of this repo in Atom, and you can see some of the key formatting features.

Go to https://guides.github.com/features/mastering-markdown/ to learn more about Markdown syntax.

## Exercise

Create your very own repo! If you don't already have a repo for your R code and analyses for your PhD project, this could be a great chance to make one. You may prefer to keep this repo 'Private' as the work is ongoing and unpublished.

Alternatively, you could create a repository based on the `Example-readme.md` file in the Evocell github.
