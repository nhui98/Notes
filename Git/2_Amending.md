# Looking at Commits
git show <commit>           //show commit and contents
git show <commit> --stat    //show files changed in the commit
git diff                    //show unstaged changes
git diff --staged           //show staged changes
git branch [--merged | --no-merged] master    //show which branches are merged or not with the master branch

# Fixing Mistakes
git checkout -- <file>            //OVERWRITES the working area with the file in the staging area*
git checkout <commit> -- <file>   //OVERWRITES the stage area to match commit + OVERWRITES the working area to match the staging area
git checkout <deleted-commit>^ -- <file>  //can use to restore a deleted file

git clean -dry-run          //list untracked files in working directory to be deleted       
git clean -d --dry-run      //list untracked files and directories
git clean -d -f             //delete untracked files and directories

git revert <commit>         //create new commit that reverts the changes of the specified commit

git reset --soft HEAD~1     //moves HEAD back to previous commit
git reset HEAD~1            //moves HEAD back to previous commit, copies commit changes to the staging area
git reset --hard HEAD~1     //moves HEAD back to previous commit, copies commit changes to the staging area and copies it to working area
* dont reset commits that are already pushed on a public repository

# Changing the previous commit
git commit --amend          //combine the current and previous commits into a new commit
*amend any commit*
git commit --fixup <SHA>
git rebase -i --autosquash <SHA>^

# Reflog
git reflog