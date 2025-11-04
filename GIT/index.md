# GIT 

## Everyday uses commands

- When needed : `git push --force-with-lease`
- When i want to unstage files : `git reset`

## Setting git parent pointer to a different parent branch
Instead of cherry-picking commit from branch with parent is the wrong branch use
- checkout on the feature branch then `git rebase --onto good-parent-branch feature-branch`

## Gorgeous log
- `git log --oneline --decorate --graph --all`
- `git log --pretty=format:"%h - %an, %ar : %s"   `


## Amend with no message change
`git commit --amend --no-edit --date=now`

## Co-Authors
([from pix](https://github.com/1024pix/pix))

```text
# Team Accès 🫶
#
# Co-authored-by: Anne-Marie E. <email1@example.net>
# Co-authored-by: Clément L. <email2@example.net>
```

- Enregistrer le template ci-dessous dans un fichier dans le dossier utilisateur (par exemple `~/.gitmessage`)
- Informer git de son existence avec la commande `git config --global commit.template ~/.gitmessage`

## Commit de fixup

- Find sha from commit to fix with `git log --oneline` 
- git add .
- git commit --fixup <votre_sha1_de_commit>
- git rebase -i --autosquash <votre_sha1_de_commit>~ (le ~ est très important !)
- git push --force-with-lease

https://medium.com/just-tech-it-now/git-commit-fixup-corriger-editer-un-commit-simplement-dd6c7d9026cd






