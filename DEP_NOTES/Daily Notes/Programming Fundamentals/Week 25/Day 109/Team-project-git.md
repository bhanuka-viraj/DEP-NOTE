how to create a branch -> `git branch <branchname[<commitsha>=HEAD]>`
how to list  branch -> `git branch`
how to list remote branch -> `git branch -r`
how to list remote/local branches -> `git branch -a`
how to delete a branch -> `git branch -d <branch name>`
how to delete a branch forcefully -> `git branch -d -f <branch name>`, `git branch -D <branch name>`
To switch a branch -> `git switch <branch name>`

how to get the log and the graph of the branches -> 
`git log --oneline --graph --all`

![[Pasted image 20240805193027.png]]
how to create a new branch and switch to it -> 
`git switch -c <branch name> [<commit sha value>] = head`

how to identify the current branch -> 
`git branch`
`git log --oneline --graph --all`
`git status`

what is the naming convention for the branch name -> 
`<issuename>/1/taskname`

How to fetch all branches from cloud  to remote-> 
`git fetch --all`

How to get one branch from cloud to remote ->
`git fetch <branch name>`

How to get a branch from remote repository to a local repository 
`git switch <remote branch name>`
`git switch -C <branch name> <remote branch name>`

==Q.==What is fast forwarding merge
==A.== 
`git merge <traget branch name>`
This is not considered as a best practice in industry , because it is difficult to find whether a merge is happen or not. In other merge strategies, a merges commit is added to the branch. 

How to merge a branch ->
First move to the branch that is  current branch is need to be merged with. (destination branch).
`git merge --no-ff <branch name>`


==Interview Question -> ==

Q. What is the merging method of git
A. Three way merging

Q.What does mean three way merging
A. This squares are the 3 ocations are checked

![[Pasted image 20240805221443.png]]

