# Lear Git

In this repo, i explain how use the git in command line.


## Init a repository
\
To use a repository git local, is need start this repository with following  command.
```bash
git init 
```
**"git init"** will create a ".git" directory in the current directory. From then on, all files in this directory will be monitored by git and can be checked.

## git config
\
Identification is required to perform push and commits on git. However, git has 3 types of configuration:


- **git config  --system:**
    - for all users on system and your repositoryes;
    - `/etc/gitconfig` (Linux);
    - `C:\Program Files\Git\etc\gitconfig` (Windows).
- **git config --global:**
    - only current user;
    - ~/.gitconfig ou ~/.config/git/config;
    - On Windows, in directory $HOME C:\Users\$USER
- **git config:**
    - for directory of the project;
    - .git\config

## Global Configuration
\
View the configuration

```bash
git config --list
```
\
![Command "git config --list"](img/git%20config%20list%20command.png)



```bash
git config --global user.name <USER NAME>
git config --global user.email <MAIL>
```

![Command "git config --global"](img/git%20config%20clogal%20command.png)
