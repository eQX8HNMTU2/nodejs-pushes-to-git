# NodeJS pushes to Git

I was bored one day, and I decided use git in a remote server to add, commit, 
and push lines of randomly generated code to a repository that is hosted on both [Bitbucket](https://bitbucket.org/andihamolli/nodejs-pushes-to-git/) and on [Github](https://github.com/AndiHamolli/nodejs-pushes-to-git/).

## How does it work?

To not spam the main branch, the bot will create a new branch each time it does a commit to the remotes.

The nodeJS bot, basically executes shell commandes via `exec` module of nodejs. I did some interesting improvements to *promisify* the use of `exec` and I might publish that into a repository in the future, as it worked really well.

I also wrote about this side project [here](https://andi1.herokuapp.com/side-projects.php), and at the time speaking there are 141 branches avaiable. :D

### Update

To also make commits to the master, but without adding extra stuff to the master, I create two files to add to master, then commit and push, then move to a branch, then commit and push to that branch, then return to master again, and then delete the files from master locally and push again. This way, my commits to the `default` branch on github are shown on the github commit graph.
