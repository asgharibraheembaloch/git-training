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
- #### to track changes for your changes
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
>> - `` `git push -u origin main` will remove necessity for every time write long this code -u stands here for making it upstream``
