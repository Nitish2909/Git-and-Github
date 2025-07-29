# what is git ?
 Git is a verson control system(vcs). It  help to track all the changes in code . It is popular, open source ,fast and scaleble.It is used for:
 <br>
Tracking code changes.
<br>
Tracking who made changes.
<br>
Coding collaboration.
<br>

# Key Git Concepts:

1.Repository: A folder where Git tracks your project and its history.
<br>
2.Clone: Make a copy of a remote repository on your computer.
<br>
3.Stage: Tell Git which changes you want to save next.
<br>
4.Commit: Save a snapshot of your staged changes.
<br>
5.Branch: Work on different versions or features at the same time.
<br>
6.Merge: Combine changes from different branches. 
<br>
7.Pull: Get the latest changes from a remote repository.
<br>
8.Push: Send your changes to a remote repository.
<br>

# Working with Git :

1.Initialize Git(git init ) on a folder, making it a Repository.
<br>
2.Git now creates a hidden folder (in your project folder)to keep track of changes in that folder.
<br>
3.When a file is changed, addedor deleted, it is considered modified.
<br>
4.You select the modified files you want to Stage(git add <filename>).
<br>
5.The Staged files are Committed, which prompts Git to store a permanent snapshot of the files(git commit -m "write some message").
<br>
6.Git allows you to see the full history of every commit.
<br>
7.You can revert back to any previous commit.
<br>
8.Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!


# Some basic  git commands :

```bash

To check hidden file :
ls -a  


To check what is inside hidden file :
ls .git


To create a file inside a folder :
touch file_name

To check what is written in the file : 
cat file_name

```

#  How to set username and password in git:

```bash

git config --global user.name "abc"

git cofig --global user.password "abc123"

```

# some Common git commands:

<b>How to initialize </b>

```bash

git init  

```
Initialize a new Git repository.
<br>
It creates a <b>.git</b> folder in your project folder .it starts track changes in code from here.

<b>How to clone a repo</b>

```bash

git clone <url>  

```
Clone a repository from GitHub Means makes a local copy of a remote project.

<b>How to check status of file:</b>

```bash

git status    

```
 Show the status of your files.
 <br>
Tells you which files are:
<br>
Untracked (new)
<br>
Modified (changed but not committed)
<br>
Staged (ready to commit)

<b>How to add file or folder </b>

```bash

//It is used for add a single file.

git add <file>   
    
if you want to add all files :

git add .
    
```
When file is add by using this command.After that the file is staged and ready for commit (means save all the changes)


<b>unstage a file by using this command</b>

```bash

git restore --staged <file>

```    

<b>How to commit the changes</b>

```bash

git commit -m "Message" 

```
Here The -m stands for "message" .It allows you to add a commit message directly in the command line without 
<br>
opening a separate text editor.Save your changes with a message.
<br>
git commit:-
<br>
A git commit is a command in Git that captures a snapshot of the project's currently staged changes, creating a permanent record in the repository's history.

<b>How to connect your local  git repo to remote repo(like github)</b>

```bash

git remote add origin <url>

```
Here,
<br>
git remote add  -> Add a new repository.
<br>
origin  -> The default name for the remote.
<br>
url  -> The URL of the remote repo (on GitHub, GitLab, etc.)


<b> How to push a local repo to remote repo</b>

```bash

git push origin main  

```
push changes to GitHub.
<br>
here the breakdown of this command:
<br>
git push  => Push (upload) changes
origin   => The name of the remote (default is 'origin')
main  =>The branch you're pushing to (usually 'main' or 'master').default branch is main.
<br><br>

Note :-
<br>
If it's your first push, you may need:

```bash

git push -u origin main   

//Here The -u sets the upstream so next time you can just use:

git push

```

<b>To fetch the latest file from remote repo</b>

```bash

git pull origin main 

```
<b>to check branch</b>

```bash

git branch

```
It shows current branch 

<br>

<b>To check commit is done or not by using this command :</b>

```bash

git log

```

<b>To see what has changed in your code before committing it by  using :</b>

```bash

git diff   //it tells what difference between older version of code or new version of code.

```

<b>To check old files by using this:</b>

```bash

git show  id:fileName

Example:

git show  e9f4d6dabe91548277ae655721403dd261dd10d7 :README.md

```

<b>Get old version of code by using <b>git checkout</b> command. </b>

```bash

git checkout 

```

<b>Common uses of git checkout command :</b>

1. Switch to another branch :

```bash

git checkout main

```

2. Create and switch to a new branch (legacy way):

```bash

git checkout -b feature-login

```

3. Restore a specific file to the previous committed version.

```bash

//for specific file using their id and file name

git checkout id --fileName


//for all files

git checkout *

```

4. Restore a specific file to the last(current) committed version.

```bash

git checkout breanchName -- *  //branch name like main

```

# Negative Cases

<b>If we made any change by mistake and save it</b>
<br><br>
Case1: To undo changes, get the last successful change

```bash

git restore . or filename ( here . mean all files)

```
Case2: If we added the changes using git add then..

```bash

git restore --staged <file_path>   ///To unstage


git restore <file_path> //To discard changes in the working directory

```
Negative Cases


Case3: Added changes to staging area (didn't commit) after this added more changes to file

```bash

//To get the staged changes

git restore --worktree index.html

```
Case4: How about if we did commit also wrong files.

```bash

git reset --soft HEAD^ (uncommit and keep the changes)


git reset --hard HEAD^ (uncommit and discard the changes)

```

# Useful Log Options :

```bash

git log -p -2   (last two commit with diff) p stands for patch


git log --stat (summary of changes)


git log --pretty=oneline  (it show one commit in one line)

git log --pretty=format:"%h - %an, %ar : %s"  

| Placeholder | Meaning                               |
| ----------- | ------------------------------------- |
| `%h`        | Abbreviated commit hash               |
| `%an`       | Author name                           |
| `%ar`       | Time since commit (e.g., 2 hours ago) |
| `%s`        | Commit message                        |



git log -S function_name      //This command helps you search your Git commit history for where a specific 
                               string(like a function name) was added or removed.


 git log --grep="fix bug"  (search commit msg)


git log --since="2024-01-01"

git log --until="2024-01-01"


git log --author="Paul"

git log --no-merges

 ```

 # Remote Repository 

 A remote repository is a version of your project hosted on the internet or a network — usually on platforms like GitHub, GitLab, Bitbucket, etc.
<br>
A remote repo is an online copy of your project that lets you collaborate with others, back up your code, and share it.

# Here the steps(command) line by line to push new file or folder from local to remote repo:

```bash

git init 

git add .

git commit -m "some message"

git remote add origin <url> (of remote repository)

git push -u origin main

```
# Some Common Git Remote Commands :

```bash

git remote                    -> Lists the short names of all remotes (e.g., `origin`) 
                     
git remote -v                  -> Lists remotes with their URLs for fetch and push       
                
git remote add <name> <url>     -> Adds a new remote connection to your repo (e.g., GitHub)                   

git remote remove <name>         -> Removes a remote (disconnects it)                                        

git remote rename <old> <new>    -> Renames a remote (e.g., rename `origin` to `github`)       

git remote show <name>            -> Shows detailed info about the remote (branches, fetch/push URLs, tracking) 

git push <remote> <branch>        -> Pushes your local branch to the remote repo          

git push -u <remote> <branch>     -> Pushes and sets the remote branch as the default (upstream) 

git pull <remote> <branch>         -> Fetches and merges changes from the remote branch to local

git fetch <remote>                -> Downloads commits from the remote but doesn't merge         

git clone <url>                     -> Copies a remote repo to your local system                 

git set-url <remote> <new-url>      -> Changes the URL of a remote repo                          

git push <remote> --delete <branch>  -> Deletes a branch from the remote repo                     
    
git push <remote> :<branch>       -> Alternate way to delete a remote branch              

git fetch --all                -> Fetches updates from all configured remotes                              

    
```

# Important Point :

If your local repository does not contains the commit which are on online repository and you want to push some changes to online repo. then it does not work. Then in this case you need to push it forcefully .

```bash

git push origin main -f 

Here f means forcefully.

```

# How to revert commit in remote repo :

If we have pushed an undesired code to remote repo then we can revert it by using :

```bash

git revert "hash_of_that_particular_commit"

// "hash_of_that_particular_commit" will be the hash of that commit which have done by mistake. 


// revert : It creates a new commit that undoes the changes made by the specified commit. But history of that commit is preserved.  


// once we have revert in local repo we need to push it to remote repo. 


// we can revert multiple commits 

git revert head~3..head~0 

// it will revert last three commits. 

```

# Branching and Merging :

<b>Branching :</b>
<br><br>
A branch in Git is like a separate workspace where you can develop new features or make changes without affecting the main code (usually main or master).
<br><br>
<b>Why use branch ?</b>
<br>
1.Experiment safely
<br>
2.Work on multiple features in parallel
<br>
3.Collaborate with others without conflicts


# Some common Branch commands:

```bash

git branch      	             // List all local branches

git branch <name>	              //Create a new branch

git checkout <name>	              //Switch to a branch

git checkout -b <name>	          //Create and switch to a new branch

git branch -d <name>	         // Delete a local branch

git push origin <branch>	      //Push branch to remote

git push -u origin <branch>	      //Push and track the remote branch

```

#  Merging in Git :

git merge is used to combine changes from one branch into another.
<br>
It allows multiple developers (or yourself working on different features) to combine their work safely into a main branch (like main or master).
<br><br>

Example:
<br><br>

```bash

git checkout main            //Switch to main branch
git merge feature-login      //Merge feature-login into main

```

# Merge conflicts :

A merge conflict occurs when Git can’t automatically decide how to merge changes because the same lines of code were modified in both branches.


# Forking :

Forking is the process of copying someone else's repository to your own GitHub account

<b>Why fork?</b>

1.You don’t have write access to the original repo.
<br><br>
2 You want to propose changes, fix bugs, or add features.
<br><br>
3.You can work independently without affecting the original project.


# What is a Pull Request (PR)?

After making changes in your forked repository, a Pull Request is how you ask the original repo owner to review and merge your changes.































