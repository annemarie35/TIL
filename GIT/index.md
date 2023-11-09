## Setting git parent pointer to a different parent
Instead of cherry-picking commit from branch with parent is the wrong branch use
- checkout on the feature branch then `git rebase --onto good-parent-branch feature-branch`
