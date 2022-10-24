# GIT Cheatsheet
---

## First steps

- Initialize GIT for the project folder, the "working directory." The result of initializing a new Git repository is that Git will create a hidden folder called .git in the directory.
	- `git init`

- Set user.name and user.email.
	- `git config user.email "email@domain.com"`
	-  `git config user.name "Armando Rambo"`

- Check the **status** of the files in your working directory.
	- `git status`
	
- Check the status of **your config**.
	- ``git config --list``
	- ``git remote -v``

- Adding a new file to Git’s index does two things—it marks the file as being “tracked” and creates a copy of that file into the index.
	- `git add filename, or git add . for all files and folders`

- When you make a commit, Git creates a copy of the files in the index and stores them in the object database. It also creates a commit object that records metadata about the commit, including a pointer to the files that were just stored, the author name and email, and the time the commit was made, as well as the commit message.
	- `git commit -m "Something Descriptive"`

---

## Branches

**Create branch locally**
- Remember to create branches from the branch you want to branch from. If you want to branch from master, remember to switch to master before creating the branch.
- ``git switch -c branchname``
	- Switches to "branchname" and creates it at the same time. For the switch command to work, GIT version must be **greater than 2.23.0**. If your GIT version is older, use, `git checkout -b "branchname"`.
	
- You can also use `git branch "branchname"`

**Create branch on GitHub from the CLI**
- Install the GitHub cli tool.
	- `dnf install gh`
	- `gh repo create`
	
- Then push the existing repository from the command line to the new repo we just created using "gh."
	- `git remote add origin git@github.com:IceNetworkGitHub/name-of-repo-we-created.git`
	- `git branch -M main`
	- `git push -u origin main`

**Remove remote origin**
- ``git remote remove origin``
	- The name should be the one in your config file. To view it ``cd .git`` and ``cat config``. Should look something like this, this command deletes the two lines under [remote "origin"].
```
	[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
	[user]
	name = Rambo Stallone
	email = greatestemailever@gmail.uk
	[remote "origin"]
	url = git@github.com:githubaccount/reponame
	fetch = +refs/heads/*:refs/remotes/origin/*
```

**Switch to another branch**
- `git switch "branchname"`

**List branches**
- `git branch`
- `git branch -v` to see additional information.
- If your repo has 0 commits, it might not be listed.

**Delete branch**
- `git branch --delete branchname`

---

## Help

- git "command" --help. Longer version.
- git "command" -h. This is a much shorter version of the help page. 


## Debug
- **" ! [rejected]        main -> main (non-fast-forward)**
error: failed to push some refs to 'github.com:accountname/terraform.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
"
### Fix 
1. ``git pull --rebase origin master``
2. ```git push origin master``

---