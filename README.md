# This repo will have all info about Git that we learned

## Git branch options

1. `git branch`

List all of the branches in your repository.

2. `git branch <branch>`

Create a new branch called ＜ branch ＞.

3. `git branch -d <branch>`

Delete the specified branch. This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.

4. `git branch -D <branch>`

Force delete the specified branch, even if it has unmerged changes. This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.

5. `git branch -m <branch>`

Rename the current branch to ＜ branch ＞.

6. `git branch -a`

List all remote branches.
