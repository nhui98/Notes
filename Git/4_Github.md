*Fork*
copy of a repository that is stored in your gitHub account
*Pull Request*
ask the owner of the repository to pull your changes

Remote Branch
Remote Tracking Branch
Local Tracking Branch

git remote add origin <url>

git fetch                         //keep local repository up to date with the remote
git pull (git fetch + git merge)  //if changes happened upstream will create a merge commit, otherwise ff
git pull --rebase
git pull origin master

git push                          //send changes to the remote repository
git push -u origin master         //sets upstream between local and remote tracking branch

git branch -r                     //list all remote branches
git branch -a                     //list all remote and local branches
git branch -vv                    //list tracking branches and their remotes

git branch --delete --remote name //delete remote tracking branch
git push origin --delete name     //delete remote branch
