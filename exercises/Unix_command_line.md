# Unix Command Line

## Reading
>Chapters 4 and 5 of Haddock, SHD and CW Dunn (2011) [Practical Computing for Biologists](http://practicalcomputing.org/)

## Getting started

- Download [Docker](https://www.docker.com/) if you haven't already.

## Introduction

### Docker

Everything we can run here, we can run on your Mac OSX or a Linux machine natively without worrying about Docker. To keep things consistent, especially for Windows users, we will use docker.

Docker containers are incredibly useful - they are lightweight and fast. They provide a reproducible environment to run your code, and they're incredibly easy to use. Lots of developers provide their own docker containers which you can use to run your analyses.

We will be using the tidyverse rocker container -- this is rstudio for docker.

In your terminal, Command Prompt or PowerShell (Windows), run:
`docker run -e PASSWORD=pass -p 8787:8787 -it rocker/rstudio bash`

You are now running ubuntu.

You can exit your docker container by typing `exit`

To see a list of all the running containers, type `docker ps`. If your container is closed, you can type `docker ps -a` to get a list of all containers.

You may need to run `docker restart [container id]` to restart the container.

To transfer files to/from a Docker container, use `docker cp`:

e.g `docker cp Manuscript_prep.RData [container_id]:/Manuscript_prep.RData`

### Simple shell commands

Figure out where you are in the shell with `ls` (list). This gives you files & directories within the directory you are in.

`pwd` gives you your working directory

`cd` enables you to move around. The command `cd ..` lets you move back in the directory structure.

`mkdir` - make directories

`rmdir` - remove directories

Move into `home` and run `git clone https://github.com/cmunro/evocell.git` (we'll be getting into Git in the next lesson)

run `ls` to see what's in here. `cd` into `examples`

`cp` - copy a file  `cp reflist.txt reflist_new.txt`

You have to specify a new file name if you are copying into the same directory. But if you move out of the directory with `cd ..` you can run `cp /home/evocell/pcfb/examples/reflist.txt ./` where `.` refers to the directory you are in.

`mv` - move files

**Adding arguments**

`ls`, `cd`, `pwd` etc. are programs run by the shell. You can pass additional information to these programs in the form of arguments.

Type `ls --help` to get a list of optional arguments to modify your command. `ls -a` gives you a list of all your files in a directory.

### Using wildcards

You can also use wildcards in the terminal, especially `*`.

For example `ls C*` gives you all the files in the directory that start with C.

### Viewing file contents

This docker container does not have file viewers installed. You can view the top portion of your file with `head`, e.g `head reflist.txt` or the bottom portion of your file with `tail`.

There are a number of file viewers likely available on your clusters/servers or personal computers. Some common ones are `vim`, `vi`, and `nano`.

We will install a file viewer:
`apt-get update`
`apt-get install -y nano`

To open an existing file type `nano reflist.txt`.

### Redirecting & joining files

- You can redirect the output of a command to a file rather than the screen using `>`

In the folder `pcfb`, make a new folder `sandbox`. In here, try `ls -l ../examples/*.seq > files.txt`

- You can use `cat` to combine files. Try `cat ../examples/FEC00002_1.seq ../examples/FEC00001_1.seq` or `cat ../examples/*.seq`.

Try redirecting the output to a new file.

### Grep in the command line

You can use regex in the command line too!

Try `grep "Toolik Lake" ../examples/shaver_etal.csv > toolik1.csv`

Check `grep --help` to see other additional arguments. `grep -v` for example, gives the inverse, while `grep -i` instructs grep to ignore the case of letters in your search.

### Piping output

You can redirect the output from one program to another. Try piping `history | grep Toolik`, where `history` shows a history of past commands.

One of the pipes I use a lot is `ls -1 | wc -l`. This gives a list (`ls`) with `-1` entry per line; piped into the count `wc` of `-l` lines.

## Exercise 1

Use pipes and grep to count how many times the EcoRI cut site "GAATTC" appears in the `*.seq` files in `pcfb/examples`. (There are a few ways to do this)

### Downloading files in the command line

You can download files from the web using `wget`. Try for example, `wget "http://files.rcsb.org/view/1ema.pdb"`

## Tips

Up arrow - moves through your command history

Tab - autocompletes
