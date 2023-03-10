# UseFul Git Commands

## CLI Commands
1. `ls` list all items in a folder.
2. `cd` change directory.
3. `cd ..` change directory to upper directory.
4. `mkdir +foldername+` creates a new folder.
5. `new-file +filename+` creates a new file.
6. `rm +filename+` removes a file.
7. `rm -rf +foldername+` removes a folder.
8. `cat +filename+` prints the content of a file.

## Initial Setup
1. `git config --global user.name "username"` sets the username.
2. `git config --global user.email "email"` sets the email.
3. `git config list` shows the list of config.

## Essential Commands
1. `git init` initialize a local git repo.
2. `git status` gives the current working change of files in repo.
3. `git clone +SHA+` sets-up a remote repo in local system.
4. `git add +file+` adds a file to staging area/to track.
5. `git add .` adds all files to staging area/to track.
6. `git add -i` adds files to staging area/to track interactively.
7. `git commit -m "msg"` commits the changes to local repo.
8. `git commit -am "msg"` adds and commits the changes to local repo.
9. `git restore +file+` restores the file to last commit.
10. `git restore --staged +file+` restores the file from staging area.
11. `git restore --staged .` restores all files from staging area.
12. `git restore .` restores all files to last commit.


## Repo History
1. `git log` shows the history of commits.
2. `git log -p` history of commits with diff(contentchanges).
3. `git log -2` show latest 2 commits.
4. `git log --oneline` shows the history of commits in one line.
5. `git log --stats` shows the history of commits with stats(fileschanged).
6. `git log --pretty` shows the history of commits with pretty format.
7. `git show +SHA+` shows the details of a commit.
8. `git diff +file+` shows the diff of a file.
9. `git commit --amend` amends the last commit.
10. `git revert +SHA+` reverts the commit and by creating new revert commit.
11. `git reset +SHA+` resets/deletes the commit.
12. `git reset --hard +SHA+` resets/deletes the commit and changes the working directory.
13. `git reset --soft +SHA+` resets/deletes the commit and keeps the changes in staging area.
14. `git reset --mixed +SHA+` resets/deletes the commit and keeps the changes in working directory.

## stash
1. `git stash` stashes the changes.
2. `git stash list` shows the list of stashes.
3. `git stash apply` applies the latest stash.

## Remote Repo
1. `git remote` shows the list of remote repos.
2. `git remote -v` shows the list of remote repos with url.
3. `git remote add +name+ +url+` adds a remote repo.
4. `git remote remove +name+` removes a remote repo.

## Pushing
1. `git push +remote+ +branch+` pushes the changes to remote repo.
2. `git push -u +remote+ +branch+` pushes the changes to remote repo and sets the upstream.
3. `git push --force +remote+ +branch+` pushes the changes to remote repo forcefully.

## Branching
1. `git branch` shows the list of branches.
2. `git branch +branchname+` creates a new branch.
3. `git checkout +branchname+` switches to a branch.
4. `git checkout -b +branchname+` creates a new branch and switches to it.
5. `git merge +branchname+` merges the branch to current branch.
6. `git merge --abort` aborts the merge if there is a conflict.
7. `git branch -d +branchname+` deletes a branch.

## gitignore
1. simply create a file named .gitignore in the root of the repo.
2. add the files/folders to be ignored in the .gitignore file.
3. by writing the file/folder name/path in a new line.

## Taging
1. `git tag -a +tagname+ +SHA+` tags a commit with a tagname.
2. `git tag +tagname+` tags a current commit with a tagname.
3. `git tag` shows the list of tags.
4. `git tag -d +tagname+` deletes a tag.

## Extra Tips
1. to exit a commit log list just press => `q`
2. Working with Vim
    1. `i` => insert mode
    2. `esc` => normal mode
    3. `:wq` => write and quit
    4. `:q!` => quit without saving

