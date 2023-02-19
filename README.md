# This repo will have all info about Git that we learned
## STASH useful commands
### fixing issue There is no detailed info about Git \#1

`git stash push [(msg)]`
Save your local modifications to a new stash, and run git reset ‑‑hard to revert them. The msg part is optional and gives the description along with the stashed state. For quickly making a snapshot, you can omit both push and msg.

`git stash pop`
Applies the changes from the last (or specified) stash and then removes the given stash.

`git stash apply [(stash)]`
Move changes from the specified stash into the workspace. The latest stash is the default.

`git stash list`
List the stashes that you currently have.

`git stash show [(stash)]`
Show the changes recorded in the stash as a diff between the stashed state and its original parent. When no stash is given, shows the latest one.

`git stash drop [(stash)]`
Remove a single stashed state from the stash list. When no stash is given, it removes the latest one.

`git stash clear`
Remove all the stashed states. Note that those states will then be subject to pruning, and may be impossible to recover.


`git stash branch (branchname) [(stash)]`
Creates and checks out a new branch named branchname starting from the commit at which the stash was originally created, applies the changes recorded in stash to the new working tree and index.
If that succeeds, and stash is a reference of the form stash@{revision}, it then drops the stash. When no stash is given, applies the latest one.
This is useful if the branch on which you ran git stash push has changed enough that git stash apply fails due to conflicts. Since the stash is applied on top of the commit that was HEAD at the time git stash was run, it restores the originally stashed state with no conflicts.
