

# Git Basic

```bash
# check git version
git --version

# view command help
git <COMMAND> -help
# view all command help
git help --all
```

## Git Configure

```bash
# configure git
git config --global user.name "Xiuyuan Wang"
git config --global user.email "tom.xy.wang@outlook.com"
```

## Git Initialize

```bash
# initialize git
git init
# initiate with another name (main)
git init -b main
```

## Git Status

```bash
# check status
git status
# check status with compact way
git status --short
```

## Git Log

```bash
# view the history of commits
git log
```

## Git Branch

```bash
# create new branch
git branch <BRANCH>

# delete the branch
git branch -d <BRANCH>

# list all local branches
git branch
# list all remote branches
git branch -r
# list all local and remote branches
git branch -a

# switch to another branch
git checkout <BRANCH>

# create and switch to the branch
git checkout -b <BRANCH>

# merge the current branch with another branch
git merge <BRANCH>
```

## Git Stage

```bash
# stage the file
git add <FILE>
# stage all files
git add .
```

## Git Discard and Unstage

```bash
# discard changes in working directory
# unstage changes from staging environment
git restore <FILE>
```

## Git Commit

```bash
# commit file
git commit -m "First commit"
# commit file without stage
git commit -a -m "Second commit"
```

# Github

- Create a Repository on GitHub

## Git Remote

```bash
# add the remote repository as an origin to the local repository
git remote add origin <URL>
# check remote repository url
git remote -v
# rename original remote repo
git remote rename origin upstream
```

## Git Push

```bash
# first time push main branch to remote repository
git push --set-upstream origin main
# push default branch to remote repository
git push
# push specified branch to remote repository
git push origin <BRANCH>
```

## Git Pull

```bash
# pull updates from default branch of remote repository
git pull
# pull updates from specified branch of remote repository
git pull origin <BRANCH>
```

## Git Clone

```bash
# clone remote repo to local
git clone <URL>
```

# Git .gitignore

- `.gitignore` file specifies which files should be ignored (untracked) by Git.
- `.gitignore` file is tracked by Git.
- `.gitignore` file in subdirectory only applies to that subdirectory.

**Rules for `.gitignore`**

| Pattern                          | Explanation/Matches                                          | Examples                                                     |
| :------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
|                                  | Blank lines are ignored                                      |                                                              |
| # *text comment*                 | Lines starting with # are ignored                            |                                                              |
| *name*                           | All *name* files, *name* folders, and files and folders in any *name* folder | /name.log /name/file.txt /lib/name.log                       |
| *name*/                          | Ending with / specifies the pattern is for a folder. Matches all files and folders in any *name* folder | /name/file.txt /name/log/name.log  **no match:** /name.log   |
| *name*.*file*                    | All files with the *name.file*                               | /name.file /lib/name.file                                    |
| */name*.*file*                   | Starting with / specifies the pattern matches only files in the root folder | /name.file  **no match:** /lib/name.file                     |
| *lib/name*.*file*                | Patterns specifiing files in specific folders are always realative to root (even if you do not start with / ) | /lib/name.file  **no match:** name.file /test/lib/name.file  |
| ***/lib/name.file*               | Starting with ** before / specifies that it matches any folder in the repository. Not just on root. | /lib/name.file /test/lib/name.file                           |
| ***/name*                        | All *name* folders, and files and folders in any *name* folder | /name/log.file /lib/name/log.file /name/lib/log.file         |
| /lib/***/name*                   | All *name* folders, and files and folders in any *name* folder within the lib folder. | /lib/name/log.file /lib/test/name/log.file /lib/test/ver1/name/log.file  **no match:** /name/log.file |
| *.*file*                         | All files withe *.file* extention                            | /name.file /lib/name.file                                    |
| **name*/                         | All folders ending with *name*                               | /lastname/log.file /firstname/log.file                       |
| *name*?.*file*                   | ? matches a **single** non-specific character                | /names.file /name1.file  **no match:** /names1.file          |
| *name*[a-z].*file*               | [*range*] matches a **single** character in the specified range (in this case a character in the range of a-z, and also be numberic.) | /names.file /nameb.file  **no match:** /name1.file           |
| *name*[abc].*file*               | [*set*] matches a **single** character in the specified set of characters (in this case either a, b, or c) | /namea.file /nameb.file  **no match:** /names.file           |
| *name*[!abc].*file*              | [!*set*] matches a **single** character, **except** the ones spesified in the set of characters (in this case a, b, or c) | /names.file /namex.file  **no match:** /namesb.file          |
| *.*file*                         | All files withe *.file* extention                            | /name.file /lib/name.file                                    |
| *name*/ !*name*/secret.log       | ! specifies a negation or exception. Matches all files and folders in any *name* folder, except name/secret.log | /name/file.txt /name/log/name.log  **no match:** /name/secret.log |
| *.*file *!*name*.file            | ! specifies a negation or exception. All files withe *.file* extention, except name.file | /log.file /lastname.file  **no match:** /name.file           |
| *.*file *!*name*/**.file* junk.* | Adding new patterns after a negation will re-ignore a previous negated file All files withe *.file* extention, except the ones in *name* folder. Unless the file name is junk | /log.file /name/log.file  **no match:** /name/junk.file      |

# Git Undo

## Git Revert

- Return to a previous `commit` and add it as a new `commit`.

- Find the return point:

  ```bash
  # view commit history in oneline way
  # return the first seven characters of the commit hash and the commit message
  git log --oneline
  
  52418f7 (HEAD -> master) Just a regular update, definitely no accidents here...
  9a9add8 (origin/master) Added .gitignore
  81912ba Corrected spelling error
  3fdaa5b Merge pull request #1 from w3schools-test/update-readme
  836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
  daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
  facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
  e7de78f Updated index.html. Resized image
  5a04b6f Updated README.md with a line about focus
  d29d69f Updated README.md with a line about GitHub
  e0b6038 merged with hello-world-images after fixing conflicts
  1f1584e added new image
  dfa79db updated index.html with emergency fix
  0312c55 Added image to Hello World
  09f4acd Updated index.html with a new line
  221ec6e First release of Hello World!
  ```

- Revert to latest commit:

  ```bash
  # revert the latest change, and then commit
  # --no-edit skip the commit message editor
  git revert HEAD --no-edit
  
  [master e56ba1f] Revert "Just a regular update, definitely no accidents here..."
   Date: Thu Apr 22 10:50:13 2021 +0200
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 img_hello_git.jpg
  ```

- Check revert commit:

  ```bash
  git log --oneline
  
  e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
  52418f7 Just a regular update, definitely no accidents here...
  9a9add8 (origin/master) Added .gitignore
  81912ba Corrected spelling error
  3fdaa5b Merge pull request #1 from w3schools-test/update-readme
  836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
  daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
  facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
  e7de78f Updated index.html. Resized image
  5a04b6f Updated README.md with a line about focus
  d29d69f Updated README.md with a line about GitHub
  e0b6038 merged with hello-world-images after fixing conflicts
  1f1584e added new image
  dfa79db updated index.html with emergency fix
  0312c55 Added image to Hello World
  09f4acd Updated index.html with a new line
  221ec6e First release of Hello World!
  ```

- Revert to earlier commit:

  ```bash
  # revert back to the third latest commit (9a9add8)
  git revert HEAD~2 --no-edit
  ```


## Git Reset

**Definition**

- Move the repository back to a previous `commit`, discarding any changes made after that `commit`.

**Operation**

```bash
git log --oneline

e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
52418f7 Just a regular update, definitely no accidents here...
9a9add8 (origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```

```bash
# reset to previous commit
git reset 9a9add8
```

```bash
git log --oneline

9a9add8 (HEAD -> master, origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```

```bash
# reset back to the lastest commit
git reset e56ba1f
```

```bash
git log --oneline

e56ba1f (HEAD -> master) Revert "Just a regular update, definitely no accidents here..."
52418f7 Just a regular update, definitely no accidents here...
9a9add8 (origin/master) Added .gitignore
81912ba Corrected spelling error
3fdaa5b Merge pull request #1 from w3schools-test/update-readme
836e5bf (origin/update-readme, update-readme) Updated readme for GitHub Branches
daf4f7c (origin/html-skeleton, html-skeleton) Updated index.html with basic meta
facaeae (gh-page/master) Merge branch 'master' of https://github.com/w3schools-test/hello-world
e7de78f Updated index.html. Resized image
5a04b6f Updated README.md with a line about focus
d29d69f Updated README.md with a line about GitHub
e0b6038 merged with hello-world-images after fixing conflicts
1f1584e added new image
dfa79db updated index.html with emergency fix
0312c55 Added image to Hello World
09f4acd Updated index.html with a new line
221ec6e First release of Hello World!
```

## Git Amend

**Definition**

- Combine changes in the `staging environment` with the latest `commit`, and create a new `commit`.
- The new `commit` replaces the latest `commit` entirely.

**Operation**

```bash
git commit -m "Adding plines to reddme"

[master 07c5bc5] Adding plines to reddme
 1 file changed, 3 insertions(+), 1 deletion(-)


# Update the message of the latest commit
git commit --amend -m "Added lines to README.md"

[master eaa69ce] Added lines to README.md
 Date: Thu Apr 22 12:18:52 2021 +0200
 1 file changed, 3 insertions(+), 1 deletion(-))
```
