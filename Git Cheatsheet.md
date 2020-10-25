## Git Cheatsheet

### Initializing and Removing Git Repositories
<code>git init</code> : Initialize a repository.  
<code>rm -rf .git</code> : Removes Git version from the folder.

<code>git status</code> : Checks the status of the git repository.
>This provides information on:
>* Where the HEAD is pointing.
>* **Files that have been changed but not committed.**
>* **Files that are in the staging area.**
>* Outlines any merge conflicts and point to files that are the issue.

### Adding
<code>git add [name]</code> : Adds specified file to the staging area. 
> Multiple files can be chained together : <code>git add [name] [name] [name]</code>  
><code>git add .</code> : This will add all untracked files and any files that have been changed to the staging area.

### Deleting
<code>git rm [name]</code> : Removes specified file from the repository.  
<code>git rm -r [name]</code> : Removes folder (including all file contained within) from the repository.  
<code>git rm -r *</code> : Removes all files from repository.

### Committing
<code>git commit -m "message"</code> : Commits the file from the staging area to the branch with a message outlining changes.
>Needs to always include a message so that people can understand what has been done.
<code>git log</code> : Provides user with history of commits.  
 
### Pushing to GitHub
<code>git push -u origin master</code> : This sets the upstream so that in future pushes to GitHub you can just use <code>git push -u</code> without having to type out "origin master" as this is now the default.  
<code>git push -u [remote name] [branch]</code> : Pushes items in staging area (once committed) to GitHub on the specified [branch].

### Pulling from Github
<code>git clone [remote name]</code> : Clones the specified GitHub repository to the local computer.  
<code>git pull [remote name] [branch]</code> : Pulls the specified data from GitHub to the local repository.  

### Removing File from Staging Area
<code>git reset [name]</code> : Removes specified file from staging area.  

### Reverting to a Previous Point
<code>git checkout -- [file]</code> : Reverts file to a previous commit point.   
<code>git checkout [commit hash]</code> : Reverts to a previous commit point.   
>Check <code>git status</code> and copy the commit hash.    

### Linkage to GitHub
<code>git remote -v</code> : Displays list of remote repositories.  
<code>git remote add origin [repo]</code> : Links Git to Github.  
<code>git remote remove [repo]</code> : Remotes the remote link to Github.

### Branching
<code>git branch</code> : Shows current branchs available and branch that is being worked on currently.    
<code>git checkout [branch]</code> : Moves to a specified branch.    
<code>git branch [branchname]</code> : Creates a new branch from the Main(Master) branch.  
<code>git branch -d [branch]</code> : Deletes specified branch.  
<code>git branch -D [branch]</code> : Deletes branch (regardless of whether it has been merged).  
<code>git merge [branchname]</code> : Merges the [branchname] with the main branch.  
<code>git checkout --orphan [branch]</code> : Unlinks the specified branch from the current branch.  

### Excluding Files
<code>touch .gitignore</code> : This will create a .gitignore file.
>For files that you do not want to have pushed to Git, you enter the file and list the file(inc. extension) that you want to exclude.
