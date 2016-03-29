Git:

Git is a fully distributed version control system. Whenever a git clone is made, the complete repository is copied instead of just the lastest version. This way, even if the repository on the Git server is lost, any user's repo can be replaced with it.

Git is very speed, as almost all the operations are local. You dont need a network connection to work on your repo. You can commit code locally and push to remote remo, when you have network connection. 

Git's killer feature is its branching feature. Its very light weight and very useful for development, as one can create as many branches as they can very easily and quickly. It supports non-linear development.

Git stores each commit as a snapshot, instead of changes from the previous commit. So, in Git commits are streams of snapshots. 

Git Basics:

Git has three areas. 

1. Working Directory
2. Staging area
3. Committed area

When a git repository is created using git init or by cloning a remote git repo, a .git folder is created in your project folder. All the files or folders apart from the .git folder, comes under Working Directory. It is the place where you work on your code. Make changes, add new files, add the changes to be committed.

Staging area, as the name suggests is like a middle layer between the working directory and committed area. git add command is used to add contents to the staging area. It means, we are making our files ready for commit, by adding them to staging area. git commit command has to be run, to move the files from staging area to committed area. 

Committed area is the place where committed files are present. Git only keeps track of the committed files. Any uncommitted files in the working directory/staging area can be lost. 

Tracked/Untracked files:

Tracked files are files which are present in the previous commit. They can be unmodified, modified, or staged.
Untracked files are files which are not present in the previous commit and which are not added to the staging area. 

Object Database:

Git has four types of Objects:

1. Blobs
2. Trees
3. Commit
4. Tags

Blobs store the contents of the files in the git repo. It stores the file contents only, not even the file name. By doing this, git stores only one blob for files which have same content, even though their names are different and they are present in a different subdirectory.
Trees store the filenames, their premissions and sub directories in a directory. So, trees store the directory information.
Commit Object always points to a tree which is pointing to the root directory of the project. 
Tag object points to a commit object.

These objects are immutable and they cannot be changed. 

A commit object points to its parent commit object, if it has a parent. As I said earlier, in git commits are series of snapshots. Git's data model is a directed acyclic graph. Each commit points to its parent commit and so on. 

References:

Git repo has a folder to store references(.git/refs/). They are mutable. References are pointers to objects. There are three types of references

1. heads
2. remotes
3. tags
 
heads contain the SHA-1 code for each branch in the local repo.
remotes contain the SHA-1 code for each branch in the remote repo.
tags contain the SHA-1 code each commit a tag points to.

HEAD file contains a pointer/reference to the current branch in the local repo.

BRANCHING:

Branching is very light weight in Git as creating a branch is nothing but, creating a new reference in the .git/refs/heads/ folder which points to the last commit in the current branch. When a branch checkout is made, the HEAD pointer nowpoints to the newly created branch. When new changes are made and committed, only the newly created branch moves forward, whereas previous branch stays at the old position. 

