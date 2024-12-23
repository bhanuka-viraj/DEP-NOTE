
==Q. ==How fetch the main branch with base repo when use with the fork repo
==A.== 

-> add a new remote (called base) in this case setting the url of the base repo 
![[Pasted image 20240808132133.png]]
this is used to fetch from the base. Now we can keep our fork repo same as base repo using fetch. 

![[Pasted image 20240808132850.png]]


how to fetch from the base repo -> 
`git fetch base`

how to see the log of base ->
`git log --oneline --grpah base/main`

now merge this to the main ->
`git log merge base/main`

now shift the feature branch and then rebase. Now base of the feature branch is set to the last commit of the main branch

Note -> push URL of the base remote repo should be changed to the fork repo. Then there is only one push repo. Doesn't matter which remote ropo is used when pushing

![[Pasted image 20240808141314.png]]

![[Pasted image 20240808141326.png]]

[[What are the things need to be done in daily basis when work with the git project]]

==Q.== How to see the log of a branch in remote repo 
==A.== 
`git log --oneline --graph base/main`

when use the `git log` command in default it gives the log the local repository. When it is required to get the log of the branch in a remote repo it should be explicitly mentioned like below

![[Pasted image 20240808142040.png]]


[[Difference between GitHub Flow and Git flow]]

