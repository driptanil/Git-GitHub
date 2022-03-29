# Git Basics
- __Version control__ is a system that records changes to a file or set of files over time so that you can recall specific versions later.
- A __Repository__ contains all of your project's files and each file's revision history.

### 3 States
##### Modified
- changes are made in a file but have not been committed.

##### Staged
- a modified file is marked and is ready to get committed

##### Committed
- a snapshot of the data is permanently stored in git directory.

### Creating new Git Repository
- `git init` initialises an empty git repository in the current directory. A “.git” file is created and hidden.
![700](images/gitinit.png)
    
- `ls -a` shows all the files including the hidden files.
![700](images/ls-a.png)

- `touch hello.text` will create a file named “hello.txt”.
![700](images/touch.png)

### Git Status
- `git status` shows the status of the git repository.
![700](images/gitstatus.png)

### Git Add
- `git add <file>` stages the changes of the file.
![700](images/gitstatus1.png)

### Git Commit
- `git commit -m "<commit_message>"` commits to all the staged changes. “-m” adds name to the commit.
![700](images/gitcommit-m.png)
### Git Log
- `git log` will show all the history of all commits.
![700](images/gitlog.png)

### Git Restore
- `vim names.txt` allows editing the file in the console, when files are modified after they are needed to be staged again.
![700](images/vim.png)
- `git restore --staged <staged_file>` will remove staged changes for file from staged (only works after first commit).
![700](images/gitrestore--staged.png)

### Git Reset
- `git reset <commit_id>` will revert to the commit.
![700](images/gitreset.png)

### Git Stash
- `git stash` will neither commit the changes nor will delete all the changes, it just stores the changes somewhere else.
![700](images/gitstash.png)
- `git stash pop` will bring back all the changes stored somewhere else and will be staged.
![700](images/gitstashpop.png)
- `git stash clear` will remove all the changes that haven’t been staged or committed will be removed. 
![700](images/gitstashclear.png)

### Adding Origin
- `git remote add origin https://github.com/<username>/<repository_link>` will link the working directory to the GitHub repository. ![600](images/gitremoteaddorigin.png)

### Git Push
- `git push <repository-link>` or `git push origin` will push all the commits made in local git directory to remote repository. __Does not work, now token are used for authentication of user.__ [GitHub Personal Access Token Documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
![700](images/gitpush.png)
##### [GitHub Personal Access Token](https://github.com/settings/tokens):
![700](images/personalaccesstoken.png)
- Click on `Generate new token`
- Choose the permissions and validity of the token
- Copy the token (Store it somewhere safe)

- `git push https://<token>@github.com/<username>/<repository_link>` will push all the commits to the repository.
![700](images/gitpushwithtoken.png)
![700](images/gitpushwithtoken2.png)

##### SSH Keys:
1. Use `git clone git@github.com:<user>/<repository>.git` to clone repository. ![600](images/gitclonewithssh.png)
2. Use `ssh-keygen -o` to generate SSH key using git. ![600](images/ssh-keygen.png)
3. Use `cat ~/.ssh/id_rsa.pub` (this file contains the private SSH key) and select the contents and copy using `Ctrl + Shift + C`. ![600](images/catsshprivatetoken.png)
4. Open `https://github.com/settings/keys` (adding the private SSH key to GitHub), click on `new SSH keys`. ![600](images/newsshkeys.png) Paste the copied key in `key` section and add a `title`. ![600](images/addsshkey.png) 
5. Click on `Add SSH key`.

### Pulling Changes
- `git pull origin` will pull all the commits made in the remote repository to the local git directory.

### Cloning Repository
- `git clone <repository_link>` will download all the files in the remote repository to a local git directory.

## How to make contributions to the existing GitHub repository?

### Forking a Repository
- No one except the owner of the GitHub repository is allowed to make changes directly to the repository.
- `Fork` allows us to make a copy of the existing GitHub repository with our own ownership and in this repository, we are allowed to make changes directly.
- The original repository which has been forked is known as the Upstream URL.
  