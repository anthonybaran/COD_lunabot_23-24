# Git Basics

Distributed version control system

## git GUI

- GitKraken 
- GUI tools have limitations 
- Not always available
- Important to know how to use the command line along side GUI tools 

## Install Git

[Installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

- To view git version
`git version`  

- Set your username
`git config --global user.name "your name"`

- Set your email
`git config --global user.email youremail@email.com`

- Set your default editor 
`git config --global core.editor "code --wait"`

- open default editor to edit all global setting 
`git config --global -e`

- set vscode as your default diff viewer 
`git config --global diff.tool vscode`
`git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"`


- windows set this to true, mac or linux set to input
`git config --global core.auto input`

- to get help with a command 
full blown help
`git config --help`
refresher 
`git config -h`


# Git Workflow 

1. create/modify a file 
2. add file to staging area 
3. use commit command if files look right, files stay in staging area even after commit. 
Once add command is used again, then files in staging area are updated. 
4. Push code to github. Only commits are pushed, not files in staging area. 
***Always write a commit message***

- If you delete a file that you previously added to the staging area, 
you still have to use the add command to get rid of it from the staging area

## Commits

- ID
- Message 
- Date/time
- Author
- Complete snapshot 

## Git and github

- link your folder to a github repository 
`git remote add <name> <github repository>`

- remove a link to github repository 
`git remote remove <name>`

- view github branches
`git remote -v`

Push: uploading code to github

Pull: Downloading code from github

- Set up proper credentials to push to github
`git config --global credential.username "<githubusername>"`

- To push
`git push <github remote repository name> master`

- To copy a github repository on a local repository
`git clone <github repository link> <name of new folder>`

- update your branch to the current branch in github
`git fetch`

- Pull changes from github 
`git pull <remote repository to pull from> <which branch to pull from>`

- setup ssh key so you don't have to use your password to push

## Branching and Merging 

Used a lot when working with a team

Branching allows you to work on multiple things at the same time

- Create a branch
`git branch <branch name>`

- Switch to work on a new branch
`git checkout <branch name>`

Merging contains changes from all branches, result will be on the branch you are currently woring on.

- merging
`git merge <name of branch to merge into your current branch>`


# Git Commands 
### A lot of this can be done from vscode 

- Initialize a directory to create a new git project
`git init`
- creates a hidden .git folder where info is stored about your project history, don't touch it 

- Check status of working directory and staging area
`git status`

- check files in staging areas 
`git ls-files`

- Add files to staging area 
`git add file1.txt file2.txt`
- Add all files with .cpp extension (works for any extension)
`git add *.cpp`
- Add entire directory (careful with this, don't stage and commit binary or personal setting files)
`git add .`

- Commit code to repository( -m adds a message, make it meaningfull)
`git commit -m "description of updated code"`

- skips the staging area ( -a means all modified files -am combines -a and -m )
`git commit -am "Fixed bug"`

- Remove a file in one operation from working directory and staging area
`git rm file.txt`

- Rename a file (renames file.js to main.js and stages it)
`git mv main.js file.js`

- Viewing staged and unstaged changes (shows exact code that is changed, better to use a code editor for this)
`git diff --staged`

- View changes from working directory and staging area
`git diff`

- view differences using code editor you set for difftool 
`git difftool`

- view differences between staging area and last commit
`git difftool --staged`

- view history 
`git log`

- to show all commits, including in front 
`git log --all`

- short summary of commits 
`git log --oneline` (--reverse puts first commit on top and last on bottom)

`git show HEAD` last commit 
`git show HEAD~2` 3 commits back

- unstage files (Also brings file from last commit back to staging area) 
`git restore --staged file.txt` (use a period to restore everything to working directory)

- undo changes in your working directory 
`git checkout -- file.txt` (use a period to restore everything to working directory)

- Go to previous versions
`git checkout <commit ID or branch name>`

- view branching effect 
`git log --all --graph`

- Checkout without branching 
`git checkout <commit ID or Branch name> <file.txt,folder, or peroid>`

- override previous commint 
`git commit --amend -m "message"`
















