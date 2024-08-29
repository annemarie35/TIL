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


## Commit de fixup

- Find sha from commit to fix with `git log --oneline` 
- git add .
- git commit --fixup <votre_sha1_de_commit>
- git rebase -i --autosquash <votre_sha1_de_commit>~ (le ~ est très important !)
- git push --force-with-lease

https://medium.com/just-tech-it-now/git-commit-fixup-corriger-editer-un-commit-simplement-dd6c7d9026cd





