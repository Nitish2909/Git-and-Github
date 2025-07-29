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

# some Common git commands:

```bash

git init  

```
Initialize a new Git repository.
<br>
It creates a <b>.git</b> folder in your project folder .it starts track changes in code from here.

```bash

git clone <url>  

```
Clone a repository from GitHub Means makes a local copy of a remote project.

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

```bash

It is used for add a single file.

git add <file>   
    
if you want to add all files :

git add .
    
```
Stage a file for commit.Tells Git which file(s) you want to include in the next commit.

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

```bash

git pull origin main 

```
Pull changes from GitHub means Downloads changes from the remote main branch and merges them with your local code.


```bash

git branch

```
It shows current branch 

<br>

To check commit is done or not by using this command :

```bash

git log

```

To see what has changed in your code before committing it by  using :

```bash

git diff   //it tells what difference between older version of code or new version of code.

```

To check old files by using this:

```bash

git show  id:fileName

```

Get old version of code by using <b>git checkout</b> command. 

```bash

git checkout 

```

Common uses of git checkout command :

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



















