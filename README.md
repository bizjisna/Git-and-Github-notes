# GIT and GITHUB

•	Git is a version control system used for:
1.	Tracking changes in code
2.	Collaboration of code

###	Check version 
    
        git --version

###	Configure git
        
        git config --global user.name “jisna”
        git config --global user.email “jisnaanoop02@gmail.com”


###	Initialize empty repository on local
    
        git init


###	Check status of files
    
        git status

            U: untracked files
            A: added files (staging area)
            M: modified files (modified after commit)

###	Add untracked files i.e. put into staging area

* Add specific file
           
            git add <filename>
* Add all files
            
            git add .

###	Commit the changes 
        
        git commit -m “commit message”

###	To unstage the files
        
        git restore –staged <filename>

###	To view history of commits 
       
        git log

###	View all branches
        
        git branch
    
        git branch -a               # shows branches of both local and remote repo

###	Create new branch
    
        git branch -b “branch-name”

###	Navigate to a particular branch
   
        git checkout “branch-name”

###	Create a new branch and navigate to that branch
    
        git checkout -b “branch-name”

###	Delete a branch
    
        git branch -d “branch-name”

###	Merge branches

* Go to the branch where you want the new-branch to be merged then use,

        git merge branch-name

### Merge conflicts: 
* While merging branches it may lead to conflicts due to changes in the code which need to be resolved manually in the editor and then committed to be merged further.

 
# GITHUB

* Create remote repository

### Add remote origin 

        git remote add origin <github-repo-url>

### Push the local repo to remote

        git push origin <branch-name>

 ### Whenever we push a local branch to remote, we have to raise a PR (pull request) and then check for merge  conflicts, resolve conflicts and further merge the branches.


### To keep projects up-to-date, you need to perform the following operations:

1.	git fetch origin 

       - gets all the change history of a tracked branch/repo
			- OR

2.	git pull origin

       - It is a combination of fetch and merge
       - It pulls all the changes of remote repo into the local branch you are     pulling the changes


### Forking a remote repository (only on remote repo)

- A fork is a copy of a repository. This is useful when you want to contribute to someone else's project or start your own project based on theirs.
- fork is not a command in Git, but something offered in GitHub and other repository hosts.

### Cloning remote repo into local

- A clone is a full copy of a repository, including all logging and versions of files.

        git clone <remote-repo-URL>

### Undoing a commit

1.	git reset: This will not create a commit of undo

        git reset <commit-id>

2.	git revert: This will create a commit of undo

- This will undo the latest commit

        git revert HEAD   

- This will undo the specified commit; get commit-id using git log

        git revert HEAD~x                	# x is commit number

 
### git diff: 
- It actually shows you all the changes done in the file after doing a commit 

1. To see the changes between the previous commit and currently staged files

        git diff –staged 

    - OR

        git diff –cached
2. For seeing the changes between different branches 

        git diff branch-1 branch-2

###	Stashing the changes: 

         git stash
         git stash -u          	# untracked files
         git stash -a		    # include all files along with ignored files

- This allows you to temporarily store modified, tracked files in order to switch branches or work on something else without committing the changes to a branch.

- After stashing, you can modify files, create new commits, switch branches, and perform other Git operations.

##### Reapplying Stashed Changes

* To reapply stashed changes and remove them from the stash

        git stash pop
		
* To reapply the changes and keep them in the stash

	    git stash apply

 





