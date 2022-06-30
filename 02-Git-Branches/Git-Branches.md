# Git Branches
What is the use of __Branches__?

- When adding a feature or repairing a bug then always create a new branch.
- Never commit directly commit to the “main” or “master” branch which is the default branch of a GitHub Repository. Because in Open-Source Projects, code in “main” is used by everyone, and maybe our code may have some errors and is not finalised yet.

### Head Branch
- It is the active and the checked out branch, commits are always made in Head Branch
- By default “HEAD” points to the “main” or “master” branch. Generally, commits are made on the “HEAD” inside the “.git” folder.

### Local Branches
- The branches present in the local machine.

### Remote Branches
- The branches present in remote location.

### Creating new Branch
- `git branch <branch_name>` creates a new local branch.
![700](/images/gitbranch.png)
- `git branch <branch_name> <revision_id>` creates a new local branch at the commit with revision_id
  ![700](/images/gitbranch2.png)
  ![700](/images/gitbranch3.png)

### Switching Branches
- `git checkout <branch>` or `git switch <branch>` is used to change “HEAD” which will now point to the branch.
![700](/images/gitcheckout.png)

- Now commits are made to the checked out branch and the “main” or “master” branch remains unchanged.
![700](/images/git21.png)
![700](/images/git22.png)

### Renaming Branches
##### Local Branches
- `git branch -m <new_branch>` will rename the current head branch.
  ![700](/images/gitbranch-m.png)
- `git branch -m <branch> <new_branch>` will rename the branch.
  ![700](/images/gitbranch-m2.png)

##### Remote Branches
### Git Merge
- `git merge <branch>` is used to update and merge all the changes made in the “feature” branch to the “main” or “master” branch.
![700](/images/git23.png)

### Publishing Branches
- `git push -u origin <branch>` will push the local branch to remote.
  (`-u` helps establish a tracking connection)
  ![700](/images/gitpush-uorigin.png)
  ![700](/images/gitpush-uorigin2.png)
##### Tracking Connection
- By default, branches in git have no relation with each other. 
- `git checkout --track <remote_branch>` helps establish a tracking connection and adds the remote branch to locally.
  ![700](/images/gitcheckout--track.png)
- `git branch --track <branch_name> <remote_branch>` helps establish a tracking connection which allows branch to track remote branch.
  ![700](/images/gitbranch--track.png)
- It allows `git push` & `git pull` in place of `git push origin <branch>` and  also informs about unpulled and unpushed files using `git branch -v`.

### Pulling Branch
- `git pull` will pull all the changes in remote branch to local branch.

### Pushing Branch
- `git push` will push all the changes in local branch to remote branch.
  ![700](/images/gitpush2.png)

### Deleting Branch
- `git branch -d <branch>` will delete the branch, but it will not remove the branch which is currently head.
  ![700](/images/gitbranch-d.png)
  ![700](/images/gitbranch-d2.png)
- `git branch -D <branch>` will force delete the branch with not pushed files.
  ![700](/images/gitbranch-D1.png)
- `git push origin --delete <branch>` will remove delete remote branches.
  ![700](/images/deleteremotebranch.png)
  ![700](/images/gitpushorigin--delete.png)

### Merging Branch
- `git merge <branch>` integrates the changes of the branch in the local head branch.
  ![700](/images/merge.png)
  ![700](/images/mergebranch1.png)
  ![700](/images/gitmerge.png)
  ![700](/images/mergebranch2.png)

### Rebasing Branch
- `git rebase <branch>` integrates the changes of branch with the local head branch.
  ![520](/images/rebase.png)
  ![700](/images/rebasebranch1.png)
  ![700](/images/gitrebase.png)
  ![700](/images/rebasebranch2.png)

### Comparing Branches
- `git log <branch>..<another_branch>` displays the commits which are made in a branch but not in other branch.
  ![700](/images/comparingbranches.png)
  ![700](/images/gitlogbranch.png)
