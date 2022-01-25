> Written by Gautham S, CSIR-NIO, Goa, India ;
> Written on : 22/Jan/2021 ; 
> Modified on : 24/Jan/2021
___

# Basics of git

## 1. Installing git on ubuntu/debian.

```sh
sudo apt install git-all
```

## 2. Customizing your git environment.

### 2.1. Setting Identity (username and password).

##### `With option --system`
* This will configure the envirnment for all the users in the system.
* Configuration will be stored in [path]/etc/gitconfig.

```sh
git config --system user.name "name"
git config --system user.email "email_id"
```

##### `With option --global`
* This will configure the envirnment for current user in the system.
* Configuration will be stored in ~/.gitconfig or ~/.config/git/config.

```sh
git config --global user.name "name"
git config --gloabl user.email "email_id"
```

##### `With option --local`
* This will configure the envirnment for current repository.
* Configuration will be stored in .git file.
* This is the default option.

```sh
git config --local user.name "name"
git config --local user.email "email_id"
```

### 2.2. setting default editor for message.
[See more](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config#ch_core_editor)

```sh
git config --global core.editor "vim"
```

### 2.3. Change the default branch name (master).

```sh
git config --global init.defaultBranch <new_default_branch_name>
```

### 2.4. View the current configuration.

```sh
git config --list --show-origin
```

### 2.5 Saving your credential while using https connection

#### `Setting credential in remote repository url`

```sh
https://Username`**:**`Password`**@**`github.com/myRepoDir/myRepo.git`
```

#### `using credential.helper`

```sh
git config --local credential.helper store 	# To store permenently.

git config --local credential.helper 'cache --timeout=10800'	# Store for next 3 hours.
```
This will store the username and password in .git-credentials file.

[Read more](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)





## 3. Help in git

#### There are three ways to see the help.
1. git help <command>
2. git <command> --help
3. man git-<command>

## 4. Ignoring Files in git.

You can create a .gitignore file in your repository and add the name of the files which you dont want to track by git.

#### .gitignore rules

[see more](https://git-scm.com/docs/gitignore)


## 5 Creating a new git repository in your local machine

### 5.1 Turn your current folder into a repo 

```sh
git init
```

### 5.2 View the status of the repo
```sh
git status
```

### 5.3 Adding files to the index (staging)

```sh
git add <filename>			    # Add specific file.
git add --all				    # Add all files.
git add *				    # Add all files.
git add .			    	    # Add all files in the current folder.
```

### 5.4 Commit changes to head (local repository)

```sh
git commit
git commit -m "commit message"
git commit -a 				    
```

### 5.5 view the commit IDs

```sh
git log
git log --all
git log --all --decorate --graph
git log --oneline
```

### 5.6 Compare different commit

```sh
git diff
git diff --staged
git diff --cached
```

### 5.7 Removing a file from git (Removing it from your staging area)

```sh
git rm
git rm --cached
```

### 5.8 Saving uncommitted modifications using git-stash

* git-stash can be used to to save the modifications without a commit when you want to move out of the current branch.
* You can reapply the changes whenever you required.


```sh
git stash
git stash pop
```

[Read more](https://git-scm.com/docs/git-stash)



### 5.9 Moving a file (renaming)

```sh
git mv <current_name> <new_name>
```

### 5.10 Switch between commit

```sh
git checkout <commit_id>
```

### 5.11 creating a New branch

```sh
git branch <branch_name>
```

### 5.12 View Branches

```sh
git branch
```

### 5.13 Renaming a branch

```sh
git branch -m <old_branch_name> <new_branch_name>
git branch -m <new_branch_name>
```

### 5.13 Switch from one branch to another

```sh
git checkout <branch_name>
```
### 5.14 Merging two branches
* There are different **Merge Strategies** in git. 
	* Fast Forward
	* Recursive
	* Ours
	* Octopus
	* Resolve
	* Subtree

[see more](https://www.geeksforgeeks.org/merge-strategies-in-git/)
```sh
git merge <branch_name>
```

