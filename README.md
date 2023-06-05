# GIT Basics Command
Source - [https://pages.github.ibm.com/chandergovind/git-workshop-2023/](https://pages.github.ibm.com/chandergovind/git-workshop-2023/)

### Creating a repo (locally/CLI)
```
mkdir test_repo_folder
cd test_repo_folder
```
Initialize a repo with
```
git init
```
Add some file to the folder
```
touch helloworld.c
```
Staging changes: Add the files that you want to track
```
git add helloworld.c
git commit -m "first commit"
git status
```
Ustaging files -  Untrack the files
```
git rm --cached
```
Ignoring Files (binary files - that cannot be tracked by commit or anything that can be generated from the files you already have or jpeg files or pdf files)
```
nano .gitignore
```
In the .gitignore file add the type of files you do not want to track (a.out, *.pdf, *.jpeg)
```
git add .gitignore 
git status
git commit -m "added .gitignore file"
```

### To see logs
```
git log
```
To see commit contents
```
git show <commit id>
```
To refer to the latest commnit
```
git show HEAD
git show HEAD~1
```

### Setting author name and email
```
git config --global user.name "<name>"
git config --global user.email "<email>"
```

### Branching
To check your working branch
```
git branch
```
To create a new branch
```
git checkout -b testing
```
To switch to a different branch
```
git checkout master
```

### Creating a Remote
1. Create a repo in [https://github.com](https://github.com/?q=gi)
2. git add remote origin <url>
   ```
   git remote add origin https://github.com/<git-usernamr>/git-workshop-IRL-2023.git
   ```
3. 
``` 
git branch -M master
```
4. 
```
git push -u origin master
```
5. After changing some files in the new branch, push the changes to the remote
```
git push --set-upstream origin testing
```
### To generate a ssh key
In the terminal
```
ssh-keygen -t ed25519 -C <email-id>
```
Add your ssh key to [https://github.ibm.com/settings/keys](https://github.ibm.com/settings/keys)

### Open, review and merge a PR
To merge the changes of a branch with the main branch

### Delete a Branch
git branch -d <repo-name>

### Create issues 

### Issue based workflows
1. Creates an issue first.
2. Then open a branch using the number of the issue.
3. Include the issue number in the commit that fixes the problem.
4. Open a PR and when it is merged in, the issue is also closed.

### Additional commands
```
git stash
git reset --hard
git reset --hard HEAD~1
git reset --soft HEAD~1
```

### To replace a old commit message with a new one
```
git commit --ammend
```
After pushing to repo, we can also modify the prev commit message. but simple push with given an error
```
nano myFile2.txt
git add myFile2.tx
git commit --amend
git push
git push --force
```

### Staging parts of a file
```
git add -p helloworld.c
git commit -m "fix in func1"
```