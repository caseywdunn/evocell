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

### Shortcuts

Up arrow - moves through your command history

Tab - autocompletes
