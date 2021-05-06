## Git states
Git handles files in different states:
- Untracked;
- Unmodified;
- Modified;
- commited.

In addition to these four states, Git files reside in one of three areas:
- the working directory
- the test area
- git directory (also known as your local repository). Note that a repository is just a sophisticated name for a versioned folder. 

Manipulation between all of the above states occurs locally, which means that the changes do not affect anyone else's current repository other than yours (we will discuss remote repositories - or those that are located on a server - soon). 

![Area of files on git](img/area%20of%20files%20on%20git.png)

The first step is to define and create a directory for the repository.
```bash
mkdir projeto_git
cd projeto_git
```

and

```bash
git init
```

Git creates the .git directory with the default files to work on the project

![Git default files on project diretory](img/git%20default%20file%20on%20project%20directory.png)

Creating a README.md file for initial information about the repository
```bash
echo "Information about repository" > README.md
```

Checking the repository state
```bash
git status 
``` 
![Checking the repository state](img/git%20status.png)

The README.me file was identified as Untracked, that is, unmarked. The means that git has identified a new file created in the project directory, but has not yet checked to enter version control. To add it, we can do:
```bash
git add README.md
```
The files are now marked and ready for a commit.
![git add](img/git%20add.png)

A warning message is displayed regarding the line terminations. This is because the configuration environment is Windows, which has a line-terminating character that is distinct from other operating systems. This character will be changed in the git project, but it remains the same in the working directory.

Viewing git status again.
```bash
git status
```
![git status again](img/git%20status%20again.png)

The new file is already identified as staged, that is, marked for commit. So let's do the commit, which is nothing less than creating a version for this file.

```bash
git commit -m "My first commit"
```

![git commit](img/git%20commit%20-m%20message.png)


We can see that the tree is clean. 

So far, we've seen the untracked and stage stages of the file. Let's meet the modified.

```bash
echo "Add a new line" >> README.md
```

And check the git status again
```bash
git status
```
![git status again again](img/git%20status%20again%20again.png)

Git has already identified that the README.md file has been modified and displays the following two options:

- **git add <FILE>**: add the change to be committed;
- **git restore <FILE>**: discard changes made to the file;
- **git add** or **git commit -a:** allows you to add the file and already commit afterwards

```bash
git add README.md
git commit -m "Add again a new line"
```

Checking changes before commit
```bash
echo "Add a third line" >> README.md
git diff
```
![git diff](img/git%20diff.png)

### **Tip**: to avoid problems and rework when operating git repositories, follow the flow below.

- **git status**: before making changes;
- **modify**: make the desired change;
- **git diff**: compare before and after the change;
- **git add**: add the file that has been changed;
- **git commit -m**: commit;
- **git log**: view changes after commit;
- **git show <HASH COMMIT>**: check details of a specific commit.

The git log displays the information for all commits, in order of the most recent commit to the most recent.

![git log](img/git%20log.png)

To view details of a specific commit, simply use the commit hash:
```bash
git show de3d02e215370b134864a3fa171db314752d443b
```

![git show](img/git%20show.png)

```bash
git log --decorate --oneline
```

Git allows you to customize the view of the commit logs with the **--decorate** and **--oneline** option to view on a single line.

![git log decorate oneline](img/git%20log%20decorate%20oneline.png)

In this format, only part of the hash is displayed.

When working with more than one **branch**, their view is best displayed with the `--graph` option.

```bash
git log --decorate --oneline --graph
```

![git log decorate oneline graph](img/git%20log%20decorate%20oneline%20graph.png)

Other types of log display:
- Displays the log in a reduced format: 
```bash
 git shortlog
```

- Displays the amount of commits per author:
```bash
git shortlog -sn
```

Reference:

- [https://snipcademy.com/git-fundamentals](https://snipcademy.com/git-fundamentals)