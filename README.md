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
