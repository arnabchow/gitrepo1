# gitrepo1
# Hello Everybody Myself Arnab Chowdhury. First of all I would like to thanks Vimal Sir to Delivering such a wonderful training on Devops Assemblyline, I am very grateful to Sir and also waiting more knowledge on Devops Assembly line program.

Home Work Summary

JOB#1

If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2

If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.

Both dev-docker and master-docker environment are on different docker containers.

JOB#3

Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2
# Solution:

Here I am using 3 jobs (i.e devjob1, qajob1 and prodjob1) to archive my goal.
As per requirement developer is develop one webpage and once commit in local git, it will automatically trigger this devjob1 by using trigger function (i.e.Trigger builds remotely) and also push to github as well in dev1 branch and a test page is deployed.
Now we have one job called prodjob1 which only run when final commit happen in master branch after QA is qualified and final web page is deployed in Live. Here we are using one trigger called "GitHub hook trigger for GITScm polling" and that we are using ngrok helping webhook for github.
Now third job called qajob1 which main job is to check the dev website , if it was working fine the do git merge and deploy the web pages in live , technically qajob1 will trigger prodjob1. Here I am using prodjob1 is downstream project.
