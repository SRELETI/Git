## Git Commands

###### Staging files 
**git add** - adds untracked files and tracked modified files to staging area. It can take <filename> or --all as options. 

###### Committing files
**git commit** - It will commit the staged files. It needs a madatory message for each commit.

###### Committing by skiping the git add command
**git commit -a -m "message"** - It will stage the files and commit them.

###### View the status of files in your repo.
**git status ** 

###### "Diff" vs "status".
**git diff** checks the difference between the previous commit and the working directory

###### "Diff" on staging area
**git diff --cached** checks the difference between the previous commit and the staging area.

###### Remove files from the working directory
**git clean -df** will clean the working directory. It removes files from the working directory
**git reset HEAD --hard** will reset the working directory to the last commit.


###### Remove Files
**git rm <filename>** will remove the file from the working directory and stages the change. So, it means the user doesnt have to run the "git add" command again. This is the main difference when compared with the normal rm command.
**git rm -f <filename>** will remove the file which is already staged. It removes the staged file and stage the modification. 
**git rm --cached <filename>** will remove the file from the staging area, but not delete the file from the file system. This is useful when you forgot to add something to the .gitignore list.

###### Git Config
**git config** is used for configuring the git installation. There are three levels at which git can be configured. 

###### Ignore files
**.gitignore** file is used to ignore the files that are added to it.

	1.Repository Level
	2.User level
	3.System wide
(.git/config) file is the repository specific file
(~/.gitconfig) file is the user specific file
(/etc/gitconfig) file is the system wide file

The repo specific file overrides the user specific file and user specific file overrides the system wide file.

**--system** flag will set the system wide configuration.
**--global** flag will set the user specific configuration.
**--local** or no flag will set the repo specific configuration.

**OPTIONS**

**user.name, user.email, core.edit, color.ui, alias.<somename> command**

**git config --list** List all the configurations 

**git config <keyname>** will list the value for the key.

**GIT CLONE **
**git clone --bare** will create the repo without a working directory. Repositories on GitHub are also bare repositories. 

**git clone <repo url> <reponame> will create a local repo with a different name compared to the remote repo.

###### Git add Interactive
** git add -i** Interactive way of adding files to the staging area. 


###### Git Log
Shows the history of commits. Its fast, as everything is local.
**git log**

**git log -pretty** Its a useful way to print the output of log command

**-pretty oneline, short, medium, full, fuller, email, raw,format** Different options for pretty.

**-n, --since, --until, --author** are some of the options that can be used with log. 

###### Git Show:
**git show commitname**
**git ls-tree commitname**

**git push local branch to remote branch**

git push -u origin feature_branch_name

 
###### Git submodules:
Git submodules are typically used when you want to access another git repo in your code. For example, if you are using a library or has some dependency on other repo in your code, then you can access that code in your repo using submodules. 

**git submodule add url** will add a repo as submodule to your local repo.

**git clone url** will clone a project with submodule, but the submodule will be empty. **git submodule init** and **git submodule update** has to be run to get data into it.

**git clone --recursive url** will clone a project with submodule and also init and update the submodule for you. 

**Working on the submodule is same as how you do for a normal repo**

**git push --recurse-submodules=check** will push the submodules first and then push the main repo.

###### Made Changes in Wrong branch

Made changes in master branch instead of making changes in a topic branch.

**git stash**

**git checkout topic_branch**

**git stash apply**

