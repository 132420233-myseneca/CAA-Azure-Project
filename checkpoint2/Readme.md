# Checkpoint2 Submission

- **COURSE INFORMATION:** CAA900
- **STUDENT’S NAME:** AdIMABUA TEDDY NWABUISI
- **STUDENT'S NUMBER:** 132420233
- **GITHUB USER ID:** 132420233-myseneca
- **TEACHER’S NAME:** ATOOSA NASIRI
  
# Table of Contents

- [Part A - Adding Files - Local Repo Workflow](#adding-files-local-repo-workflow)
- [Part B - Inspecting Local Repo with `git status` and `git log`](#inspecting-local-repo-with-`git-status`-and-`git-log`)
- [Part C - Creating & Merging Branches](#creating-&-merging-branches)
- [Part D - Git Branching Strategy Review Question](#branching-strategy-review-question)



## Adding files local repo workflow
 - [git-status-untracked](https://github.com/132420233-myseneca/CAA-Azure-Project/blob/main/checkpoint2/git_status_untracked.txt)
 - [git-status-uncommited](https://github.com/132420233-myseneca/CAA-Azure-Project/blob/main/checkpoint2/git_status_uncommitted.txt)
 - [git-status-committed](https://github.com/132420233-myseneca/CAA-Azure-Project/blob/main/checkpoint2/git_status_committed.txt)

 ##  Inspecting Local Repo with `git status` and `git log`
   #### `git log`
   - **Purpose:** This is a command on git used to show to show commit history,it is ran with a command `git log`,it also shows the the author of the
     commit,the date and as many number of commit you want to it to display

- **Example:**
 `commit 934ea9acbb39538e9d2f646ebff495e5dcf53c96 (origin/main, origin/HEAD)
Author: “132420233-myseneca” <“nwabuisiteddy@yahoo.com”>
Date:   Sun Jan 28 23:11:37 2024 -0500
adds footnotes folder`

#### `git status`

- **Purpose:**
  - This command is used to show the status of changes in a directory we are currently working on with Git. It helps to show if the files are tracked, uncommitted, or committed.
- **Example:** This is a exapmple of a committed git repository
`On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_status_committed.txt

nothing added to commit but untracked files present (use "git add" to track)
`

  


 

## Creating & Merging Branches
``` bash
$ git log -n 5

commit a71c040d8ac2ddb768849626c237eed6aa25f422 (HEAD -> main, feat-emojis/feat-emojis, feat-emojis)
Author: “132420233-myseneca” <“nwabuisiteddy@yahoo.com”>
Date:   Sun Jan 28 23:17:23 2024 -0500

 adds emojis to feat-emojis branch

commit 934ea9acbb39538e9d2f646ebff495e5dcf53c96 (origin/main, origin/HEAD)
Author: “132420233-myseneca” <“nwabuisiteddy@yahoo.com”>
Date:   Sun Jan 28 23:11:37 2024 -0500

    adds footnotes folder

commit 20fa06efb103ea9ea9be248f541e61f7a7171f23
Author: “132420233-myseneca” <“nwabuisiteddy@yahoo.com”>
Date:   Sun Jan 28 22:51:04 2024 -0500

    made some mistakes in the file,so i corrected

commit 44d8b14d265fc1b17ed54a8b6acbb4413811a704
Author: “132420233-myseneca” <“nwabuisiteddy@yahoo.com”>
Date:   Sun Jan 28 22:41:35 2024 -0500
```

## Branching Strategy Review question

### Differences between develop branch and main branch 
From the article the the develop branch is a part of the main branch which consists of the master and develop branch

- **Master:** This is also know as the master branch from the documentation provided;The code in this branch just simply denoted codes which can be sent to production;it also only accepts merge from the Hotfix and Release branch
- **Develop:** This branch denotes the active development branch in which where work is doneit accepts merge from the hotfix,release and bugfic branch
### Three supporting branches and their functions

### Supporting branches include:

- **Bugfix/feature branches:** This branch was created to introduced for the purpose of fixing of bugs and also for intoducing new features,it must created from the develop branch and merge back into the develop branch
- **Hotfix branches:** This branch was designed to resolve emergent problems in during production.it can be merged into the develop or master branch
- **Release branches:** Branches with short life span used to prepare releases. This particular branch should be a branched off tagged `develop` and merge back into master, as well as the develop branch. That branch is created used just to increment the version and do some last minute prep work.

### Best practices in working with release branches

- Only create a realese branch if all intended feature and the bugfix branches are reconciled in the develop branch, and if it is practically almost ready for production
- The release branch should  be used to bump the version number and perform last minute citation 
- When the release branch is made ready, merge into master, tag with version number and finally merge back to develop.

  






