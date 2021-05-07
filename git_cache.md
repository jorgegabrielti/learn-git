# Removing file in cache

Git allows removal of files from both the directory and the git repository itself. For that, we will use the command git rm.

Considering the following .gitignore file

```bash
*.csv
*.log
*.txt
!.conf
```

Let's add a new file to the repository and commit.

```bash
echo '{"nome": "Name", "age" : "29", "tasks":[ {"task1" : "1"}, {"task" : "2"}, {"task" : "2"}]}' > profile.json
```


```bash
git status
git add profile.json
git commit -m "profile.json [add]"
```

After the commit, someone might think: "To remove, just add the file to gitignore". Lets test:

```bash 
echo "profile.json" >> .gitignore
git status
git log --oneline
git show <ID-COMMIT>
```

Just adding to .gitignore was not enough. We now have two options, we can completely remove the file or just remove it from git.

Completely removing the file.
```bash
git rm profile.json
```
To return the file to the directory.


```bash
git log
git reset --hard <ID-COMMIT>
```

To remove only from the git repository
```bash
git rm --cached profile.json
```
![git status git cache](img/gitcache/git_status.png)



