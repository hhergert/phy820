---
title: "Git Repositories"
date: 2019-08-13T03:32:49+02:00
weight: 2
draft: false
---

## Installing Git

If it is not already installed on your system (just try typing `git --version` in an open shell/terminal on your computer), you can download the latest version of Git from the [official website](https://git-scm.com). The documentation section of the site has a good overview of how to get started and the basic workflows for committing source code, pushing to and pulling from repositories, etc. If you haven't used Git before, you can try out the basic steps while you set up your own repository on [MSU's GitLab server](http://gitlab.msu.edu) for the homeworks, as described below.


## Setting Up Your Project Repository

We will use a simple workflow for submitting computational homework via Git. Follow these steps to set things up: 

1. 	Log into [MSU's GitLab server](http://gitlab.msu.edu) with your NetID, and create a new project named
	**PHY820FS21** (the name is simplified for convenience). 

2. 	Go to the **project settings** via the side menu, and add me (NetID: hhergert) as a project member with 
	Developer permissions. This will allow me to actively push modifications to your project (e.g., fixes) if necessary, rather than just comment on your code.

3. 	Clone the project to your local machine (`git clone`). This will also set up the associations for pulling and pushing code from and to your repository on the GitLab server. For convenience, you can get the URL for your repository by clicking on the **Clone** button on your GitLab project screen. Check your repository associations to see if everything was set up properly - you should get the following output:

	```bash
	$ git remote -v show 
	origin	https://<your netid>@gitlab.msu.edu/<your netid>/phy820fs21.git (fetch)
	origin	https://<your netid>@gitlab.msu.edu/<your netid>/phy820fs21.git (push)
	```

	or
	
	```bash
	$ git remote -v show 
	origin	git@gitlab.msu.edu:<your netid>/phy820fs21.git (fetch)
	origin	git@gitlab.msu.edu:<your netid>/phy820fs21.git (push)
	```

{{%notice note%}}
If you are going to primarily access the repository from an off-campus network, you should use the HTTPS link. The SSH version will only work if you are connecting from MSU Wireless or some other campus network. 
{{% /notice %}}



## Workflow for Projects

If you do not specify otherwise, your local work will be committed to the repository's `master` branch, which will get pushed to `origin/master`. Under the default settings of a GitLab project, this branch is protected, i.e., the owner is the only user allowed to push chode changes. 

To allow the instructors to push suggested changes (and not just review your work via the web forms), and to facilitate tracking, we will use a branch with the cleverly chosen name `submit` to submit your homework each week. 

### Starting a Project

1. 	Perform a `git pull` from the course repository to get the most recent version of the initial Jupyter notebooks for a numerical project.

2. 	On your computer, copy the Jupyter notebook to the folder that contains the **local working copy of your own project repository** (which should be **separate from the one into which you cloned the materials repository**). 

3. 	Switch to the folder containing your local working copy and type (**notice the dot**)

	```
	git add .
	```

4. 	Now type

	```
	git status
	```

	It should tell you that a new file has been added, or some tracked files have changed.

5. 	Type

	```
	git commit -m “<some message>"
	```

	This will add the current version of the notebook to your local repository. After you’ve made some changes, repeat steps 2 through 4.

6. 	Push new commits to the GitLab project by typing

	```
	git push
	```

	The default setting is to push the currently checked out branch to a the remote branch it tracks -- most likely local `master` to remote `master` branch. You can check the tracking for different branches using `git remote -v show`.

### Submitting a Project
When you are satisfied with the state of your project, it's time to submit. 

1. 	First, check which branch is currently active in your local working copy by typing

	```
	git branch
	```

	This command will show you all local branches, and highlight the current one with an asterisk and color. You can create new branches with

	```
	git branch <new branch name>
	```

	and switch to that branch via

	```
	git checkout <new branch name>
	```

	If you have created any new branches that you want to store, the command is 

	```
	git push origin
	```
	
	(which will create a new branch of the same name at the remote location), or 

	```
	git push origin <specific branch name>
	```

	which will push the local branch to a remote branch with a specific, possibly different name.

2. 	If you are submitting for the first time, create the `submit` branch

	```
	git branch submit
	```

	and check it out:

	```
	git checkout submit
	```

3.	When it is created for the first time, the `submit` branch will be identical to your local `master` branch, 
	so you can go ahead and directly push it to the GitLab server. This will create a copy of the `submit` in your
	remote repository, and associate it with the local working copy for pushing and pulling. 

	At later times, your local `master` branch will likely contain more work than the `submit` branch, so you'll have to merge them. While making sure that `submit` is checked out, type

	```
	git merge master
	```

	As the command suggests, this will merge the most recent changes from `master` into your `submit` branch. 
	Most of the time, the merge operation simply amounts to replacing a file with a newer version. If that is 
	not possible, `git` will notify you of a merge conflict and ask you to resolve it by editing the affected 
	files (see [official documentation](https://git-scm.com)).

4. 	When you’re ready to hand in the project, make sure that the recent changes to the `submit` branch have been 	
	committed (via `git status`), and push the branch to the GitLab server.


### Iterating on a Project
After submission, I will review your project and make suggestions through code comments, or maybe fix small mistakes in the source. When I am done with the review, I will push my changes to the `submit` branch of the repository.

1.	To retrieve the reviewed copy, check out the `submit` branch and pull from the remote repository.

2.	By typing

	```
	git log
	```

	you can verify that my commits appear in the history of the repository. You can then look at my changes directly
	in the submit branch, and potentially merge them into your `master` branch by running

	```
	git merge submit
	```

	with `master` being currently checked out.


More details on the workflows and commands can be found in the [official documentation](https://git-scm.com), in particular the “Getting Started” section.


<!-- ### General Workflow

The workflow for any computational homework looks like this:

1. Perform a `git pull` from the course repository to get the most recent version of the materials, including any Jupyter notebooks for a numerical homework problem.

2. Carry out your work, creating branches and commiting code as needed.

3. When ready to submit, commit your work to the `submit` branch.

4. Push the submit branch to the GitLab server by the beginning of class on the homework due date.

 -->