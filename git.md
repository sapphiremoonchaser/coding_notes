### Setup

`git config --global user.name "Your Name"`  
`git config --global user.email "you@example.com`

### Initialize or Clone
`git init` # start a repo in current folder  
`git clone <url.` # download an existing repo

### Branches
`git branch` # list branches  
`git branch <name>` # create new branch  
`git switch <name>` # switch to branch  
`git checking -b <name>` # create and switch

### Check status
`git status` # shows changed files, untracked files, branch

### Staging and Committing
`git add <file>` # add a file for staging  
`git add .` # add everything in current directory  
`git commit -m "msg"` # commit staged changes with a message

### Merging
`git merge <branch>` # merge branch into current branch

### Undoing
`git restore <file>` # restore file to last commit  
`git restore --staged <file>` # unstage file