# Running Docker interactively with Rstudio

Learn more about Rocker here: https://www.rocker-project.org/

Docker cheat sheet: https://gist.github.com/caseywdunn/34aac3d1993f9b3340496e9294239d3d

We have been using the bash session of rocker for all of our examples in this course. We can also use Rstudio interactively.

Run:

`docker run -e PASSWORD=pass -p 8787:8787 rocker/rstudio`

Note, you may need to stop the bash session by running docker stop [container ID] (you can always restart it).

Now point your browser to `http://localhost:8787/auth-sign-in`

username: rstudio
password: pass

Now you can run R Studio in your browser. You can also use git to move analyses in and out of the container

Why would you do this?
- gives you a clean, reproducible environment to test your code.
- you don't have to worry about dependencies breaking your code in the future
- multiple users could access the same webserver
- enables you to combine docker with Amazon web services (https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html)

You can find many already built docker images on https://hub.docker.com/
