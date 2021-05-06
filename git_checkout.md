# Reverting changes

## gitcheckout
\
The gitcheckout command is used to revert a change made to a given file before it is committed. In other words, gitcheckout reverts the state of a modified file back to the stage area. This is very useful for correcting errors or changes before a commit.

For example, let's add one more line to our exercise file, which has four lines.

```bash
echo "Add next line" >> README.md
```

And check status
```bash
git status
```

The file left the stage area and went to modified.

![git status](img/git_checkout/git_status.png)

However, when running **git diff**, we see that the change that was made is wrong! We need to fix it before going to the commit.

```bash
git checkout README.md
git status
```
![git checkout](img/git_checkout/git_checkout.png)

Ok, git checkout changed the state of the file from modified to stage again.

**Note**: if you have incorrectly added a directory with several sub-directories, use the command **git restore --staged** as shown in the example below.

```bash
git restore --staged .
```

Reference:

- [https://git-scm.com/docs/git-checkout](https://git-scm.com/docs/git-checkout)