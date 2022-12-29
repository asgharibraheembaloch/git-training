# Git and Github Demo

this repo contain code and files created in order to learn git basics

## Link to Tutorial 

video link is https://www.youtube.com/watch?v=RGOj5yH7evk

> ### commands used

- #### to create directory
>> `mkdir folder_name`
- #### naviagte into directory
>> `cd`
- #### initialize git within empty folder
>> `git init`
- #### cloning repo from github
>> `git clone https://github.com/asgharibraheembaloch/git-training.git`
- #### to check status on changes within files and folder in current directory
>> `git status`
- #### to track all files inside folder
>> `git add .`
- #### to track specific file relative to path
>> `git add index.html`
- #### to commit(or save) those changes
>> `git commit -m "this placeholder is for message title for what i have changed" -m "this placeholder is for message description"`
- #### to push local changes to github
>> `git push oringin main`

### to publish local repo to github
> first make local folder and then within this folder run following commands
>> - `` `git init` will initilize git repo within folder``
>> - `` `git status` will check status of changes within folder`` \
> make remote repo on github and then add conect it with your local repo
>> - `` `git remote add origin https://github.com/asgharibraheembaloch/remote-repo.git` will make connection with local and remote repos``
>> - `` `git remote -v` will check any remote repository connected with local repo``
>> - `` `git push origin main` will push code from local repo into remote repo``
>> - `` `git push -u origin main` will remove necessity for every time write long this code -u stands here for making it upstream next time use just, git push``

### concept of master and feature brach
> if you want to make changes in an experimental way that your main or master branch won't affect by those changes then you create *feature branch* this branch conatins all the details of *master branch* at the time of commit but when you make changes to feature branch this will never affect master branch neither changes in master branch will affect feature branch, from this first commit both will start their journy seprately and independent of each other, in feature there may be time when you satisfy that we have to merge code from feature branch into master branch this stage is called merge stage
> *hot fix branch* is similar to feature branch but conceptually it is way to fix bug within hot fix branch then merge it back into master or main branch

>> - `` `git branch` to check on which branch you currently``
>> - `` `git branch -c feature-readme-instructions` will create new branch based on main branch -b stands here for to instruct create a new branch``
>> - `` `git branch` will list all branch on your repo * sign indicate that you are on this branch currently on terminal ``
>> - `` `git checkout main` you will checkout on main branch or switched to main branch now any changes you will make will be reflected on main branch``

