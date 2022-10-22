# This repo will have all info about Git that we learned
## Git reset: difference between --mixed, --soft and --hard
`git-reset` - reset current HEAD to the specified state.

So, we have a branch master with this series of commits:
`A - B - C`
1. When we run `git reset --soft B`, master (and thus HEAD) now points to `B`, but the index still has the changes from `C`; git status will show them as staged. So if we run git commit at this point, we'll get a new commit with the same changes as `C`.
2. When we run `git reset --mixed B`, master and HEAD point to `B`, but this time the index is also modified to match `B`. If we run git commit at this point, nothing will happen since the index matches HEAD. We still have the changes in the working directory, but since they're not in the index, git status shows them as unstaged. To commit them, you would `git add` and then commit as usual.
3. And finally, `git reset --hard B` changes your HEAD and index (point to `B`) and also modifies your working directory. If we're at `C` and run `git reset --hard B`, then the changes added in C, as well as any uncommitted changes you have, will be removed, and the files in your working copy will match commit B. Since you can permanently lose changes this way, you should always run git status before doing a hard reset to make sure your working directory is clean or that you're okay with losing your uncommitted changes.
