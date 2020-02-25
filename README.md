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
6. git stash --include-untracked : keep untracked files, this  will stash even files not tracked by git yet, if you apply them untracked files will still be untracked.
7. git stash --all:  stash all files(even ignored ones), use with caution.
8. git stash save "WIP: making progress on something": name stashes for easy reference 
9. git stash branch {optional branch name} : start a new branch from a stash 
10. git checkout {stash name} -- {filename} : grab a single file from a stash
11. git stash pop: remove the last stash and apply changes, doesnt remove if there's a merge conflict
12. git stash drop: remove the last stash 
13. git stash drop stash@{n}: remove the nth stash 
14. git stash clear: remove all stashes.
15. git stash -p : let you selectively stash changes

==============References===========

References are pointers to commits. 
There are 3 types of git references 
- Tags and annotated tags 
- Branches : a pointer to a particular commit
- HEAD : how git knows what branch you are currently on and what the next parent will be, its a pointer and 
to the 
name of the current branch. But it can point to a commit too (detached HEAD). To see what the head is pointing to
write: cat .git/HEAD

- Tags
   - **Lightweight Tags**: Simple pointers to a commit. When you create a tag with no argument it just captures the value in     HEAD 
         * git tag my-first-commit: will create a new tag and point it to value in HEAD
  
- **Annotated Tags** : it also points to a commit but stores additional information like author, message, date.
   - git tag -a {tag name} -m {message}
   
   - git tag: to list all the tags in a repo
   - git show {tagname}: get all the info about the tag
   - git show-ref --tags: list all tags and what commit they are pointing too
   - git show-ref --points-at {commit} : list all tags pointing at a commit 

- **Branch vs Tag**: branch pointer changes with every new commit but the commit a tag is pointing to is a snapshot like v1.1 or something and it doesnt change once created.


==== HEAD-LESS/DETACHED HEAD======
This happens when you checkout a specific commit or a tag, which means HEAD will start pointing to a commit.
if you checkin a commit and you dont do anything to reference it, it gets lost means they are dangling commits which will be 
garbage collected so create a branch out of last commit.

1. git branch {new branch name} {commit}: create a branch that points to **last** commit in the detached state. This creates a permanent reference.

==== Merge Commits===

Are just commits but have more than one parent.

* git cat-file -p { commit number } this will show you the parents for a commit 

=====Miscellaneous===
1. git show-ref --heads : to show what commits all the existing branches point to.
2. git --no-pager log --oneline: so that logs open in same terminal without pagination
 
