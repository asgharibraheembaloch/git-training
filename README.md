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

### concept of main and feature brach
> if you want to make changes in an experimental way that your main or master branch won't affect by those changes then you create *feature branch* this branch conatins all the details of *master branch* at the time of commit but when you make changes to feature branch this will never affect master branch neither changes in master branch will affect feature branch, from this first commit both will start their journy seprately and independent of each other, in feature there may be time when you satisfy that we have to merge code from feature branch into master branch this stage is called merge stage
> *hot fix branch* is similar to feature branch but conceptually it is way to fix bug within hot fix branch then merge it back into master or main branch

>> - `` `git branch` to check on which branch you currently``
>> - `` `git branch -c feature-readme-instructions` will create new branch based on main branch -b stands here for to instruct create a new branch``
>> - `` `git branch` will list all branch on your repo * sign indicate that you are on this branch currently on terminal ``
>> - `` `git checkout main` you will checkout on main branch or switched to main branch now any changes you will make will be reflected on main branch``
>> - `` `git push --set-upstream origin feature-readme-instructions` will created new upstream branch on github and push code from this feature-readme-intructions to new branch on github with same name``
OR
>> - `` `git push -u origin feature-readme-instructions` will created new upstream branch on github and push code from this feature-readme-intructions to new branch on github with same name``

### pull data from remote main branch to local(origin) main if remote branch is ahead of local branch
`` `git pull origin main` if branch is not upstream then use this full command``
OR
`` `git pull` if branch is upstream then use this short command``

### concept of deleting feature branch
feature branch are created in order check or test changes or if updation is required and you don't want that your main branch to affected directly, then you created feature branch, after you satisfy that changes are well enough you merge this feature branch with main branch after merge completed developer don't likely use this feature branch usually then you delete this feature branch.

`` `git branch -d feature-readme-instructions` will delete feature branch`` \

if you want that this will also be deleted on remote github erver use following command

`git push origin -d feature-readme-instructions`

### compare two branches locally using dot syntax

```git diff master..feature` will compare changes within two branches`` \
OR
```git diff master...feature` will compare changes within two branches with common ancestors``

### Compare commits between two branches

`` `git log branch1..branch2` will compare commits between branch``
`` `git log branch1...branch2` will compare commits within two branches with common ancestors``

### after detail comparision merging on local

`` `git checkout main` will take head(pointer) on main branch``
`` `git merge feat_branch` will merge feature_branch into main branch``

### concept of conflict
some time there are multiple developer working on same branch and change same code again and again but a conflict arise when git doesn't know which code to keep and which to not beacause there are multiple changes on same line of code at this point you have to manually resolve this conflict

Note: normally workflow is when you create new branch this branch is based on main branch any changes you made within file system are termed into modified when you write command `git status` command at this stage you don't need `git add .`
you will only run this command when you create new file, so you directly commit with following command with `-a` tag allong with m `-a` here stands for add

`` `git commit -am ""` will add and commit at same time but only works for modified files not for newly created files``

checkout into main branch add new line in index.html and then hit following command \
`git checkout main`

you will git following error

`git
error: Your local changes to the following files would be overwritten by checkout:
        index.html
Please commit your changes or stash them before you switch branches.
Aborting
` \
at this stage make commit will resolve thi issue 

some time you want to be updated with main branch and need those changes in your feature branch you use following command

`git merge main`

you may encounter error like this 

Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.

in this case we have to manually remove markers like this 

then run following command in order to update feature branch with main

`git commit -m "updated index.html and remove marker errors"`

### undoing wrong staging before commit

add some line indo index.html

then run following command

`` `git status` will tell you curent status on changes you made``

`` `git add README` will track changes those changes you made``

`` `git status` run again this command you will see that your changes are committed``

supose if want to undo changes on index.html, then in this scenerio you have to unstage it with following command

`` `git reset index.html` will unstage index.html for upcomming commit if you did't give file name it will unstage all those privouse stage which you have done with 'git add' ``

at this stage if you do `git commit -am "changes are made to reame only"` only readme changes are commited to repo

### undoing wrong staging after commit

>> - what i have to do when i have done a wrong commit

`` `git reset HEAD~1` will reset your pointer(main branch at this stage) to one commit prvivous in the history, mean on the previous commit``

>> - what i have to do when i have done many wrong commits there is no way you know how many commits you have wrongly made, for this what you do is run following command `git log` this will give entire history of your prevoise commits, then what you will do is pick a commit from history which was stage where you have done correct commits and then choose it's SHA hash code, these commits are in reverse coronlogical order mean latest commit will be on top, then you run following command

`git reset faa43b46e28ebe9d90b4c9be4bab90a94decbc7b`

if you look at your files you will see that changes which you have made are still there

these changes are not saved in git or staged with git no longer, but remember that git still keep track of those changes after this hash, but what if you want completely reset to point in time where you want to keep start your new commits you will run following command

`` `git reset hard faa43b46e28ebe9d90b4c9be4bab90a94decbc7b` will not just unstage changes but will be completly remove till this pointer in head(main branch on which i am)``

now if you look at your files you will see that changes which you have made are completly gone, and you are on point in time where you have not made those changes

### concept of fork
what if you want to make sugestion(developer call pr or pull request) on other person or other's repo in this situation what you will do is fork that repo make changes, commit those changes and then send pull request to the owner of the repo if sugestions are well enough owner will merge your code into his own repo other wise reject or make comment to further elaborate on the issue

fork others repo

make changes

commit changes

at this stage changes, which are committed are on my own repo

send a pull request to owner in order merge my changes on his repo branch

>> - go pull request tab and hit 'create pull request' button
>> - create comparision on my branch on which i have made changes to the owner branch on which i want to send pull request

on screen below i can also check my suggested changes

i can also compare it with my own other branch for which i want to send pull request 

i can also see tags for my pull request which owner set on it's repo in order document feature request which might be encountered as people found suggestion in next comming

if i merge the pull request i will changes which i have made on dev branch are also on master branch






