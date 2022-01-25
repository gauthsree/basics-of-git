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
