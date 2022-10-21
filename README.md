# This repo will have all info about Git that we learned
## *git merge --ff & git merge --no-ff* what is the difference?
> With --ff, when possible resolve the merge as a fast-forward (only update the branch pointer to match the merged branch; do not create a merge commit). When not possible (when the merged-in history is not a descendant of the current history), create a merge commit.

> With --no-ff, create a merge commit in all cases, even when the merge could instead be resolved as a fast-forward.

