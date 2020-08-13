<h1 align = "center">Git Fast Reference Manual</h1>



## Description


At First, you should enter your destination folder constructed .git file, and then input follow command in terminal recording to your requirement



## 1. Construct Repository
​	<font style="color:purple">$ git init</font>

## 2. Add and Restore

![git status](./pic/git_status.png)



add some changes file from Current WorkPlace to Stage Area

​	<span style="color:purple">$ git add filename </span>

​	<span style="color:purple">$ git add .</span>

restore some changes file from Stage Area to Current Workplace

​	<span style="color:purple">$ git restore filename</span>

​	<span style="color:purple">$ git restore .</span>



additional, you command that <span style="color:purple">$ rm filename</span>, if you think the file is useless.

then, delete the file in Stage Area, or restore it

​	<span style="color:purple">$ git rm filename</span>



## Commit and Restore

commit all file in Stage Area, at the same time, you should summarize message about this modify content

the message is useful, when you want to checkout and modify some commit version previous.

​	<span style="color:purple">$ git commit -m "message"</span>



modify the last commit, but don't amend published commits!

​	<span style="color:purple">$ git commit --amend</span>



Restore some changes file from Commit Area to Stage Area

​	<span style="color:purple">$ git restore --staged filenname</span>

​	<span style="color:purple">$ git restore --staged .</span>





## Commit History



![commit_detail2](./pic/commit_detail2.png)

show git status

​	<span style="color:purple">$ git status</span>



show all commits, starting with newest

​	<span style="color:purple">$ git log</span>

​	<span style="color:purple">$ git log --pretty=oneline</span>



show all git command in the commit pointed by HEAD, starting with newest.

​	<span style="color:purple">$ git reflog</span>





## Cat-file and Ls-files

view all files in Stage Area

​		<span style="color:purple">$ git ls-files</span>



view Blob object, get the Hash value of file

​		<span style="color:purple">$ git ls-files -s filename</span>



view content by Hash value of file

​		<span style="color:purple">$ git cat-file -p commit_ID</span>





## Unset and Checkout



![reset and checkout](./pic/reset_and_checkout.png)



go back or modify previous commit version

move HEAD and branch together to commit_ID or commit_ID pointed by the other branch. 

the content of Current WorkPlace and Stage Area will equal to the commit content, 

unless untracked files(new files in WorkPlace will be saved anywhere)

That mean you should save your modify file(new a branch, add and commit the file)

​	<span style="color:purple">$ git reset --hard commit_ID</span>

​	<span style="color:purple">$ git reset --hard branch_name</span>



switch/checkout between branch

​	<span style="color:purple">$ git checkout branch_name</span>		



switch/checkout  to special commit ID

​	<span style="color:purple">$ git checkout commit_ID</span>



you should new a branch to save this commit when you checkout a previous commit version, modify file, add and commit 

​	<span style="color:purple">$ git checkout -b branch_name</span>

​	



## Branch

![master_and_branch](./pic/master_and_branch.png)



usually, don't work directly in master branch. at first, you should make a new branch, then work in the branch

show all branch

​	<span style="color:purple">$ git branch</span>



new a branch

​	<span style="color:purple">$ git branch branch_name</span>



new a branch and checkout HEAD to the branch  

​	<span style="color:purple">$ git checkout -b branch_name</span>



delete some branch

​	<span style="color:purple">$ git branch -d branch_name</span>



merge a branch pointed by HEAD to some branch_name

​	<span style="color:purple">$ git merge branch_name</span>

then delete the branch_name





## Bug and Stash

There is a interrupt in your live when you are working in a bug branch. you can stash your WorkPlace

​	<span style="color:purple">$ git stash</span>



view stash list

​	<span style="color:purple">$ git stash list</span>



restore WorkPlace in Stash Area, and delete the stash

​	<span style="color:purple">$ git stash pop</span>





## Remote Repository

show all remote repository

​	<span style="color:purple">$ git remote</span>



add remote Repository adress

example git remote add origin git@github.com:michaelliao/learngit.git

​	<span style="color:purple">$ git remote add origin url</span>



push master to origin, remote repository

​	<span style="color:purple">$ git push -u origin master</span>



after git commit --amend, after

​	<span style="color:purple">$ git push -u origin master --force</span>



clone a repository from remote repository

​	<span style="color:purple">$ git clone url</span>






