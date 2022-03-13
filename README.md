<img src="https://images.ctfassets.net/em6l9zw4tzag/s2J4qM7DvYAzmqCUnC5QQ/6e5762c0794a046129e1198e5c0a8d8d/FaveTools.gif"><br>
# <img src="https://i.imgur.com/6KXBKjB.gif" width="100"> Git & GitHub <img src="https://media0.giphy.com/avatars/mwooodward/cIe5MvDvX4Vc.gif" width="100"><br>
- `git init` initialises an empty git repository in the current directory. A “.git” file is created and hidden.
![700](git1.png)
    
- `ls -a` shows all the files including the hidden files.
![700](git2.png)

- `touch hello.text` will create a file named “hello.txt”.
![700](git3.png)
- `git status` shows the status of the git repository.
![700](git4.png)

- `git add names.txt` stages the changes of the “hello.txt” file, then `git status` shows “Changes to be committed: hello.txt”. 
![700](git5.png)
    
- `git commit -m "names.txt file added"` commits to all the staged changes. “-m” adds name to the commit.
![700](git6.png)
- `git log` will show all the history of all commits.
![700](git9.png)
- `vi names.txt` allows editing the file in the console, when files are modified after they are needed to be staged again.
![700](git7.png)
- `git restore --staged names.txt` will remove “names.txt” from staged (only works after first commit).
![700](git8.png)

- `git reset <commit_id>` will revert to the commit.
![700](git10.png)
- `git stash` will neither commit the changes nor will delete all the changes, it just stores the changes somewhere else.
![700](git11.png)
- `git stash pop` will bring back all the changes stored somewhere else and will be staged.
![700](git12.png)
- `git stash clear` will remove all the changes that haven’t been staged or committed will be removed. 
![700](git13.png)

- A __Repository__ contains all of your project's files and each file's revision history.

- `git push <repository-link>` will push all the commits to the “main” branch of the GitHub Repository. __Does not work, now token are used for authentication of user.__ [GitHub Personal Access Token Documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
![700](git14.png)
- [GitHub Personal Access Token](https://github.com/settings/tokens):
![700](git16.png)
- Click on `Generate new token`
- Choose the permissions and validity of the token
- Copy the token (Store it somewhere safe)

- `git push https://<token>@github.com/<username>/<repository_link>` will push all the commits to the repository.
![700](git18.png)
![700](git17.png)
- What is the use of __Branches__?

- When adding a feature or repairing a bug then always create a new branch.
- Never commit directly commit to the “main” or “master” branch which is the default branch of a GitHub Repository. Because in Open-Source Projects, code in “main” is used by everyone, and maybe our code may have some errors and is not finalised yet.

- `git remote add origin https://<token>@github.com/<username>/<repository_link>` will link the working directory to the GitHub repository.

- `git branch feature` creates a new branch named “feature”
- By default “HEAD” points to the “main” or “master” branch. Generally, commits are made on the “HEAD” inside the “.git” folder.
![700](git19.png)
- `git checkout feature` is used to change “HEAD” which will now point to the “feature” branch.
![700](git20.png)
- Now commits are made to the “feature” branch and the “main” or “master” branch remains unchanged.
![700](git21.png)
![700](git22.png)
- `git merge feature` is used to update and merge all the changes made in the “feature” branch to the “main” or “master” branch.
![700](git23.png)
- `git push origin master` will push all the commits to the “master” branch of GitHub Repository.
![700](git24.png)
- How to make contributions to the existing GitHub repository?

- No one except the owner of the GitHub repository is allowed to make changes directly to the repository.

- `Fork` allows us to make a copy of the existing GitHub repository with our own ownership and in this repository, we are allowed to make changes directly.
![](git25.png)
![](git26.png)
- `git clone https://github.com/driptanil/DSA-Bootcamp-Java` allows us to download all the source files of the forked repository.
![](git27.png)
- The original repository which has been forked is known as the Upstream URL.
  `git remote add origin https://<token>@github.com/driptanil/DSA-Bootcamp-Java.git` adds Upstream URL.
  
- How to merge all the changes made in the forked repository to the original repository?
    - “Pull request” is a request to pull all the changes made in the forked repository to Upstream Repository,
        
        ![Screenshot_20220114_133636.png](Git%20&%20GitH%201b90f/Screenshot_20220114_133636.png)
        
        ![Screenshot_20220114_133738.png](Git%20&%20GitH%201b90f/Screenshot_20220114_133738.png)
        
        ![Screenshot_20220114_133929.png](Git%20&%20GitH%201b90f/Screenshot_20220114_133929.png)
        
- Why never commit to the “main” or “master” branch of a GitHub Repository?
    - For Example Someone wants to add 10 features, as each branch only allows only pull requests. So all the features will be added to one pull request. If the owner likes a feature out of 10 features. Then, the owner will not get an option to merge that one feature (which he likes) and it will also be hard to manage.
    - This is why when adding new features always create new branches → new pull requests.
        
        ![Screenshot_20220114_134423.png](Git%20&%20GitH%201b90f/Screenshot_20220114_134423.png)
        
        ![Screenshot_20220114_134532.png](Git%20&%20GitH%201b90f/Screenshot_20220114_134532.png)
        
    - after committing and pushing all the new changes made to the pull request branch, it automatically updates the pull requests.
        
        ![Screenshot_20220114_134602.png](Git%20&%20GitH%201b90f/Screenshot_20220114_134602.png)
        
- How to remove commits made to the pull request branch?
    
    ![Screenshot_20220114_135941.png](Git%20&%20GitH%201b90f/Screenshot_20220114_135941.png)
    
    - Use `git reset commitID`
        
        ![Screenshot_20220114_140032.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140032.png)
        
        ![Screenshot_20220114_140053.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140053.png)
        
    - Still, after `git reset` the pull request contains the previously committed changes.
        
        ![Screenshot_20220114_140221.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140221.png)
        
    - To remove this, `git push origin kunal -f` ”-f” is used to make a forced push, as commits are inter-linked.
        
        ![Screenshot_20220114_140604.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140604.png)
        
        ![Screenshot_20220114_140539.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140539.png)
        
- To merge the pull request, click on `merge pull request`
    
    ![Screenshot_20220114_140817.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140817.png)
    
    ![Screenshot_20220114_140756.png](Git%20&%20GitH%201b90f/Screenshot_20220114_140756.png)
    
    This will merge all changes made in the “kunal” branch of the forked repository to the Upstream repository.
    

### Conflicts

- But the changes made to the “kunal” in the forked repository will not show in default, as ‘kunal” branch is not the default branch which is the “main” branch.
There are 2 ways to update the forked repository:
    
    ![Screenshot_20220114_141525.png](Git%20&%20GitH%201b90f/Screenshot_20220114_141525.png)
    
    - To fetch the updates made in the Upstream repository, click on `fetch upstream`.
        
        ![Screenshot_20220114_141350.png](Git%20&%20GitH%201b90f/Screenshot_20220114_141350.png)
        
        - To fetch all the changes made upstream, use `git reset --hard upstream`, “--hard” is a confirmation. So, use it with caution.
            
            ![Screenshot_20220114_142807.png](Git%20&%20GitH%201b90f/Screenshot_20220114_142807.png)
            
    - First, `git checkout main` to point the HEAD to the ‘main” branch.
        
        ![Screenshot_20220114_141835.png](Git%20&%20GitH%201b90f/Screenshot_20220114_141835.png)
        
        - The ”main” branch has only one commit
            
            ![Screenshot_20220114_141920.png](Git%20&%20GitH%201b90f/Screenshot_20220114_141920.png)
            
        - `git fetch --all --prune`  “--all” will fetch the commits made in all the branches. “--prune” will also fetch the commits made in deleted branches.
- Finally after fetch, use `git push origin main`
    
    ![Screenshot_20220114_142958.png](Git%20&%20GitH%201b90f/Screenshot_20220114_142958.png)
    
- If anyone commits to Upstream Repository, to download the changes locally to the forked repository use `git pull upstream main.`
    
    ![Screenshot_20220114_143350.png](Git%20&%20GitH%201b90f/Screenshot_20220114_143350.png)
    
    ![Screenshot_20220114_143433.png](Git%20&%20GitH%201b90f/Screenshot_20220114_143433.png)
    
    - Now use `git push origin main` to save the changes made locally to the forked repository.
        
        ![Screenshot_20220114_143805.png](Git%20&%20GitH%201b90f/Screenshot_20220114_143805.png)
        
        ![Screenshot_20220114_143855.png](Git%20&%20GitH%201b90f/Screenshot_20220114_143855.png)
        
- `git branch temp` will create a new branch “temp” from the “main” branch.
    
    ![Screenshot_20220114_153749.png](Git%20&%20GitH%201b90f/Screenshot_20220114_153749.png)
    
    - If too many commits are made to “temp” branch
        
        ![Screenshot_20220114_154406.png](Git%20&%20GitH%201b90f/Screenshot_20220114_154406.png)
        
    - `git rebase -i 4f3b54bf569c9c7ed40c8c90e1c72d5e8ac46253` allows us to edit all the commits.
        
        ![Screenshot_20220114_154940.png](Git%20&%20GitH%201b90f/Screenshot_20220114_154940.png)
        
        Squash merges the commits to the commit made before it.
        
        ![Screenshot_20220114_155246.png](Git%20&%20GitH%201b90f/Screenshot_20220114_155246.png)
        
        After typing `:x` and pressing Enter, we will be able to edit the commit message.
        
        ![Screenshot_20220114_155454.png](Git%20&%20GitH%201b90f/Screenshot_20220114_155454.png)
        
        ![Screenshot_20220114_155539.png](Git%20&%20GitH%201b90f/Screenshot_20220114_155539.png)
        
        Again typing `:x` will exit.
        
        ![Screenshot_20220114_155645.png](Git%20&%20GitH%201b90f/Screenshot_20220114_155645.png)
        
- What are merge conflicts?
    
    ![Screenshot_20220114_161942.png](Git%20&%20GitH%201b90f/Screenshot_20220114_161942.png)
    
    ![Screenshot_20220114_162201.png](Git%20&%20GitH%201b90f/Screenshot_20220114_162201.png)
    
    - After both Kunal’s change and Rahul’s changes have been merged. There will be a conflict while pushing the commits to the GitHub repository.
        
        ![Screenshot_20220114_162305.png](Git%20&%20GitH%201b90f/Screenshot_20220114_162305.png)
        
    - To resolve this conflict, we will have to do it manually.
        
        ![Screenshot_20220114_162346.png](Git%20&%20GitH%201b90f/Screenshot_20220114_162346.png)
        
        ![Screenshot_20220114_162503.png](Git%20&%20GitH%201b90f/Screenshot_20220114_162503.png)
        
        ![Screenshot_20220114_162733.png](Git%20&%20GitH%201b90f/Screenshot_20220114_162733.png)