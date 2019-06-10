# Scripting in the Shell

## Reading
>Chapter 6 of Haddock, SHD and CW Dunn (2011) [Practical Computing for Biologists](http://practicalcomputing.org/)

## Getting started

You should be in your docker container from our last session on the Unix command line. You may have logged out of your container, in which case, you may need to restart it and run it again.

To see a list of all the running containers, type `docker ps`. If your container is there,

If your container is closed, you can type `docker ps -a` to get a list of all containers.

You may need to run `docker restart [container id]` to restart the container.

Once you have restarted it, you need to run `docker exec -it [container id] bash` to access your running container.

## Tutorial

We're going to write shell scripts - which are essentially shell commands within a text file.

In our docker container, if we navigate to `cd /bin`, we can see all the programs stored in this directory. If we type `which bash`, we can see the path to the program `bash`/

cd back to `home`, and let's make a `scripts` folder

Now you want to tell the shell where to look for your scripts. When you type a program in the command line, the shell searches `$PATH` to find something that matches.

`echo $PATH` will tell you which of these paths are checked.

### Edit your bash profile

In your Linux docker machines, you need to edit your `.bashrc` file to permanently modify your PATH (OSX users need to modify `.bash_profile`)

```
cd #This takes you to your root directory
nano .bashrc
```
Now type:

`export PATH="$PATH:/home/scripts"`

You'll need to `exit` the container and re-enter with `docker exec -it [container id] bash`

Check if this worked by typing `echo $PATH`

### Start scripting

Go to scripts and make a new text file with `nano firstscript.sh`

Type:
```
#! /bin/bash

ls -la
echo "above is what's in this folder"
pwd
echo "the date is"
date
```

`#!` is very special - this tells the shell which program you are sending the contents to. In this case, we are sending the contents to bash.

Try running the script - it doesn't work!

`ls -la` will give you the permissions

To change the permissions, run `chmod u+x firscript.sh` [chmod = change mode u= user x=executable ]

Now it should work.

## Exercise

We are going to use a combination of shell scripting and regex in Atom to copy files in bulk. In this case, you should make a script to copy only the files that contain the word 'fluorescent' or 'fluorescence' to another directory from `/home/evocell/pcfb/examples`

Go to `/home/evocell/pcfb/examples`

`grep -li fluor *.pdb` Pull out pdb files with fluorescence/fluorescent in the file.

Paste the output in Atom. And use regular expressions to modify the output

You want to have the format `cp /home/evocell/pcfb/examples/[filename].pdb` and you want to move the file to sandbox

Each line should have the format
`cp /home/evocell/pcfb/examples/[filename].pdb /home/evocell/pcfb/sandbox`

Now turn this file into a script. Create a new script in docker using `nano copier.sh` (it is somewhat complicated to move files in and out of docker, so for this example we will just create a new script).

Now run your script.
