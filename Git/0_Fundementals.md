# Configuration
git --version
git config --global user.email "email"
git config --global user.name "name"

# Referencing
^  - the parent commit
^n - nth parent commit
~  - first commit back following first parent
~n - nth commits back following only first parent

^ and ~ can be combined

# Basic
git init
git status
git log

# Staging
git add -p 
git rm <file>     //delete file in next commit
git mv <file>     //rename file in the next commit

# Staging to Repository
git commit -m | -am
git commit -v

# Stashing
*add stash*
git stash
git stash save "name of stash"
git stash --include-untracked  //git by default only stages tracked changes
git stash -p      
*show stash*
git stash list
git stash show stash@{0}  
*apply stash*
git stash apply | git stash apply stash@{0}
git stash pop      //apply latest stash and deletes it
*remove stash*
git stash drop
git stash drop stash@{n}
git stash clear
*advanced*
git checkout <stash name> --<filename>  //retrieve one file from the stash


