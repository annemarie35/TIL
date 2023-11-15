# GIT 

## Everyday uses commands

- When needed : `git push --force-with-lease`
- When i want to unstage files : `git reset`

## Setting git parent pointer to a different parent branch
Instead of cherry-picking commit from branch with parent is the wrong branch use
- checkout on the feature branch then `git rebase --onto good-parent-branch feature-branch`

## Gorgeous log
`git log --oneline --decorate --graph --all`

## Amend
`git commit --amend --no-edit --date=now`

## Co-Authors
