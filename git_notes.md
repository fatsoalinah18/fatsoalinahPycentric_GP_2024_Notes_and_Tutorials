# Git Notes
## Git Commands  

 ### Initialize a new git repository in the current directory
 
~~~
git init "Your_Git_Repo"
~~~
 ### Cloning a git repository
 
~~~
git clone https://your_git_repo_url
~~~

 ### Checking your repository's status for changes
 
~~~
git status
~~~

### Viewing changes
 ### Tracking and staging changes 

- Staging a file
~~~
git add your_file.txt
~~~

- Staging all changes in the directory
~~~
git add.
~~~

### Showing the difference between various versions of your file
- Comparing unstaged changes
~~~
git diff
~~~

- Comparing staged changes
~~~
git diff --staged
~~~

- Comparing between branches or commits
~~~
git diff branch1..branch2
~~~
- Comparing specific files
~~~
git diff <file_name>
~~~
### Temporarily saving your uncommitted changes without committing them
- Stashing changes and reverting your working directory to match the last commit.
~~~
git stash
~~~
- Applying stashed changes
~~~
git stash apply
~~~
- Listing stashes
~~~
git stash list
~~~
- Applying a specific stash
~~~
git stash apply stash@{1}
~~~
- Stashing and applying in one step
~~~
git stash save "stash description"
git stash pop
~~~
- Dropping a stash
~~~
git stash drop stash@{1}
~~~
- Cleaning untracked files
~~~
git stash -u
~~~
### Committing the staged changes with a message
~~~
git commit -m "Your Commit Message"
~~~

### Viewing commit history

- Commit history
~~~
git log
~~~

- Condensed commit history
~~~
git log --oneline
~~~

### Branching

- Creating a new branch
~~~
git branch "your_branch_name"
~~~

- Switching to a specific branch

~~~
git checkout "your_specific_branch"
~~~

- Creating and switching to a new branch

~~~
git checkout -b
~~~

- Listing all branches

~~~
git branch
~~~

### Merging a branch into the current branch

~~~
git merge "your_branch"
~~~

### Integrating changes from one branch into another
Git rebase __rewrites__ commit history to make it _linear_, __removes__ unnecessary merge commits, and it should be used with __caution__ when working with shared branches.
- __Rebasing__ your current branch onto another branch
~~~
git checkout feature
git rebase main
~~~
- Interactive rebase
~~~
git rebase -i HEAD~n
~~~
__n__ - number of commits to rebase

- Aborting a rebase
~~~
git rebase --abort
~~~
- Continuing after a conflict
~~~
git rebase --continue
~~~
- Skipping a commit
~~~
git rebase --skip
~~~
### Pushing changes to the remote directory

- Pushing changes to a specific branch
~~~
git push origin "your_branch"
~~~
- Setting up a tracking branch and pushing changes
~~~
git push -u origin "your_branch"
~~~

### Pulling changes from the remote directory

This will __fetch and merge__ changes from the remote repository into the current branch.

~~~
git pull
~~~

### Deleting a branch

- Deleting a branch locally
~~~
git branch -d "your_branch"
~~~

- Deleting a branch in the remote repository
~~~
git push origin  --delete "your_branch"
~~~

### Reverting changes

- Reversing changes in a file
~~~
git chekout -- your_file.txt
~~~

- Unstaging a file
~~~
git reset HEAD your_file.txt
~~~

- This command will reset the repository to a specific commit and discards all changes after it.

~~~
git reset --hard "commit"
~~~

