# Git

My config: [https://bitbucket.org/ghelouis/config/src/master/.gitconfig](https://bitbucket.org/ghelouis/config/src/master/.gitconfig)

- Compare branch with master, listing only files: `git diff master --name-only`

- Undo latest local commit: `git reset HEAD~`
- Go back to a previous commit, erasing all commits made after it: `git reset --hard <commit_hash>`
- Merge/rebase: [http://www.git-attitude.fr/2014/05/04/bin-utiliser-git-merge-et-rebase/](http://www.git-attitude.fr/2014/05/04/bin-utiliser-git-merge-et-rebase/)

### Tags
- Create tag: `git tag v0.0.1`
- Delete tag: `git tag -d v0.0.1`
- Push tag: `git push origin v0.0.1`
- Push tag deletion: `git push --delete origin v0.0.1`
