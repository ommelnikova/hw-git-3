# This repo will have all info about Git that we learned
## GIT bisect

The bisect command in Git is incredible for finding which commits caused certain bugs. It is very common for a repository to have thousands of commits from hundreds of developers so when a bug report comes in it can be tricky to track down which changes caused this issue. With bisect, though, this problem is trivial. 
```
git bisect start
git bisect bad
git bisect good <commit id>
```

To start a bisect you need to run three commands. The first command starts the bisect. The second command tells Git which commit is the bad commit with the bug. If you leave this blank, Git will just use the latest commit. The final command tells Git which commit is known to not have this bug.

Now after you run these three commands Git will choose the commit in the middle of these two commits and grab all the code from that commit. You can then test to see if the bug is in this commit or not. If the bug is present you just type ***git bisect bad*** and it will select the commit that is halfway between this bad commit and the last good commit. If the bug is not present then you can type ***git bisect good*** and Git will select the commit that is halfway between this good commit and the last bad commit. You keep repeating this process of typing either good or bad until eventually you are able to narrow it down to the exact commit that caused the bug.

This is amazing at narrowing down your bug search since some bugs can be really hard to track down without knowing what code was changed to cause it.



## GIT revert

The revert command simply allows us to undo any commit on the current branch.
```
git revert <commit id>
```
All you need to do is pass the commit you want to revert to the command and it will undo all changes from that commit. One important thing to note, though, is that this **only undoes changes from that exact commit**. If you do a revert on a commit from a month ago it will not undo all changes made since that commit. It will only undo the changes in that exact commit.

Another important thing to note is that using revert **does not actually remove the old commit**. Instead it creates a new commit that undoes all the changes from the old commit. This is good since it will preserve the history of your repository.

One common trick is to revert the most recent commit which can be done with the following command
```
git revert HEAD
```