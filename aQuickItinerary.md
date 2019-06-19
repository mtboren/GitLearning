## Quick Walk Through

0. Why version control vs. copies of files
    - checkpoints, history, "rollback":  incremental success
    - distribution:  have underlying structure for consistency
    - collaboration:  let's all code on the same things!
0. Cover terminology and basic concepts of Git -- see [GitLearningItems.md](GitLearningItems.md)
    - go through a few pics
    - definitions (`working directory`, `repository`, `staging area`),
    - and actions/flows (`add`, `commit`, `push`, `branch`)
0. Cover some features of GitHub -- [GitHubLearningItems.md](GitHubLearningItems.md)
    - discuss GitHub goodness
0. Demo some actions -- given below
    - see it in action
0. See other actions/definitions

### Demo items
Overview:
- We have a repository that has an open GitHub Issue, and want to add a fix in code that will resolve the issue. We will
    - clone the origin repository to a local repository
    - create a branch in which to make our changes
    - make our changes in our branch
    - stage and commit our changes locally
    - push our commit to the origin remote repository
    - see how commit messages can relate to GitHub Issues
    - merge our updated branch back into "parent" branches
    - auto-close an issue by pushing merged master branch back to origin remote repository

Do it:

- Clone a remote repository to a new, local copy of the repository
    ```
    git clone https://github.com/mtboren/githubTest0.git c:\temp\GitThings\githubTest0
    ```

- See the working directory, and the repository directory (the `.git` folder)
    ```PowerShell
    Set-Location -Path c:\temp\GitThings\githubTest0
    git config --local user.email matt@cool.com
    Get-ChildItem
    ```

- See the branches in the repository
    ```
    git branch --all
    ```

- Create new branch in local repository
    ```PowerShell
    ## checkout the branch off of which we will base our new, feature-specific branch
    git checkout dev
    git checkout -b feat_BFInvokeExpressionConcern
    git status
    ## see that there is now a new local branch
    git branch --all
    ```

- Edit some doc in working directory

- Stage changes to index / staging area
    ```
    git add .
    git status
    ```

- Commit change to local repository (to local `.git` folder)
    ```PowerShell
    git commit -m "update important file to fix #2"
    ```

- Push commit to remote repository, setting up remote-tracking for new branch (only need to `--set-upstream` once per new branch)
    ```
    git push --set-upstream origin feat_BFInvokeExpressionConcern
    ```

- See how GitHub Issue has reference from new commit, now

- Merge updated branch into `dev`, push commit to remote repository
    ```
    git checkout dev
    git merge --no-ff feat_BFInvokeExpressionConcern
    git push
    ```

- If everything is good, merge updated branch into `master`, push commit to remote repository
    ```PowerShell
    git checkout master
    git merge --no-ff dev
    git push
    ## should notice that the corresponding GitHub issue was auto-closed due to commit that referenced having fixed it was now merged to master branch
    ```

- Explore GitHub features
    - network graphs, contributors, releases, code diff views, etc.

- Open new GitHub Issue, for fun

### Other Actions/Definitions
- Update local repo from remote:
    ```PowerShell
    ## check to see if the remote has any commits ahead of what local repo has
    git remote update
    ## pull remote commits and merge them into the local repo
    git pull
    ```
- Use a GitHub Personal Access Token for programmatic Git operations:  we use a Personal Access Token for authenticating to GitHub from Git from the command line.  See [Creating a personal access token for the command line](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/) for more info on how to create/use such things
