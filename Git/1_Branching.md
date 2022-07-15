# Branching
git branch                  
git branch <branch-name>   
git checkout  
git checkout -b 
git branch -D 

# Rebase
git rebase master
- pulls in all the latest changes from master and applies all our commits on top of them
- give a commit a new parent

git rebase -i <commit>    //interactive rebase
* rebase options
pick      //keep this commit
reword    //keep commit, change the message
edit      //keep commit, but stop to edit more than the message
squash    //combine this commit with the previous one. Stop to edit the message
fixup     //combine this commit with the previous one. Use the previous commit message
exec      //run the command on this line after picking the previous commit 
drop      //remove the commit (if you remove this line the commit will be dropped too)
git rebase --abort

* rebase tip - create a copy of current branch before rebasing and reset to it if things go wrong

# Merging
git merge <branch-name>
- fast-forward  - no additional commits were made on the base branch, head moves forward, no merge commit occurs
git merge <branch-name> --no-ff //force a merge commit
git merge --abort

# Cherry Picking
git cherrypick <commit>