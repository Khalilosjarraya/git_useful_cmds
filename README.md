

<h3 align="center">Useful Git Commands</h3>



## 📝 Table of Contents

- [About](#about)
- [Installation](#installation)
- [Usage](#usage)
- [Fixes](#fixes)
- [Author](#author)


## 🧐 About <a name = "about"></a>

Useful Git Commands
These are diffrent useful git commands that most developpers need it in their daily work



### Prerequisites

Simple knowledge of running commands on Linux Terminal.


### Installation <a name = "installation"></a>


You need to install git.

On Linux
```
sudo apt install git-all
```

On Windows you can download the binary of installation from: 
```
      https://git-scm.com/install/windows
```

On Mac

```
brew install git
```


## 🎈 Usage <a name="usage"></a>

To make a git project:
```
git init name_of_project
cd name_of_project
```

Now you can add the files and folders of your prjoect
To track your poroject status
```
git status
```
To list all branches
```
git branch 
```

To switch to a branch
```
git switch name_of_branch
```

to create and switch to new branch
```
git switch -c name_of_new_branch
```

to rename a branch
```
git branch -m current_branch_name new_branch_name
```
to delete branch
```
git branch -d name_of_branch
```
if the branch is not merged to the main branch the cmd of delete will output an error message, so we need to use this cmd
```
git branch -D name_of_branch
```

we can compare between branches
```
git diff main name_of_branch
```
to merge a branch "feature_dev" into main branch, we need to switch to the main branch
```
git switch main
```
then
```
git merge feature_dev
```
or simply if we are in another  branch
```
git merge feature_dev main
```

deal with conflicts of merge 
the merge conflict is resulted when we are modifying the same file on diffrent branches
for example we are modifying the readme.md on main branch and we make other modifications of readme.md in branch feature_dev
```
git merge feature_dev
will output:
Auto-merging readme.md
CONFLICT (content): Merge conflict in readme.md
Automatic merge failed; fix conflicts and then commit the result.
```
to fix it we need to deal with readme.md by 
```
nano readme.md
then we keep the modifcations that we want and we delete the signs =====  >>>>> Head  <<<<<< feature_dev
```

working with remote repositories or Repos
to list all remote repos 
```
git remote -v 
```
to add a remote repo
```
git remote add name_of_repo Url/path 
```
## Fix Problems <a name = "fixes"></a>
everytime when you make a push, git requires an authentification, so you enter your email or username and also your password but it dosen't work!!!
here is a workaround to deal with this problem:
```
    ssh-keygen -t rsa -b 4096 -C "youremail@gmail.com"
    eval "$(ssh-agent -s)"
```
this cmd is to copy the content of file to clipboard
```
      xclip -selection clipboard < ~/.ssh/id_rsa.pub 
```
then you add that generated key on your profile (add ssh key)(follow the video: https://www.youtube.com/watch?v=5jwzAhcovMU )
now set the url of .git/config from https to ssh from your project folder
```
      git remote set-url origin git@github.com:<your_sername>/<your_project>.git
```
now problem resolved.
PS: to avoid this problem, it's better to clone the repo using ssh url from the start

## ✍️ Author <a name = "author"></a>

- [@Khalilosjarraya](https://github.com/Khalilosjarraya) - Embedded Software Engineer




