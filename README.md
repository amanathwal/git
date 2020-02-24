# git
About all the git commands 


Plumbing Commands: 
1. git cat-file -t <hash>   will tell you if the hash is a tree,blob or commit.
2. git cat-file -p <hash> : will tell you the contents of the hash

3. git ls-file -s : will tell you the details of the files in staging area

========= Staging =====
Empty Staging area is not empty it is copy of latest commit 

1. git add <filename> : to add a file to staging area
2. git rm <filename>: remove a file and put it in staging area
3. git mv <file>: rename the file


====== Stash====
Save uncommited work. The stash is safe from destructive operations.

1. git stash : stash changes 
2. git stash list: list changes/stash list
3. git stash show stash@{0} : shoe the contents of a stash 
4. git stash apply: apply the last stash
5. git stash apply stash@{0} : apply a specific stash
6. git stash --include-untracked : keep untracked files, this  will stash even files not tracked by git yet
7. git stash --all: use with caution, stash all files(even ignored ones)
 
