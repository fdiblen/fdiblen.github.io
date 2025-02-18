# git notes

## Show the commit message and short hash

```bash
git log --pretty=oneline --abbrev-commit
```

alternatively:

```bash
git log  --pretty=format:'%h --> %s'
```

## Undo last commit

[Source](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git)

```bash
$ git commit -m "Something terribly misguided" # (0: Your Accident)
$ git reset HEAD~                              # (1)
<< edit files as necessary >>                  # (2)
$ git add .                                    # (3)
$ git commit -c ORIG_HEAD                      # (4)
```

Alternative:

```bash
git revert --no-commit 0d1d7fc3..HEAD
git commit
git push
```

## Merge branches

```bash
git checkout master
git merge dev
git push origin master
```

## Push to different remote branch

```bash
git push origin master:newBranch
```

## Fetch a file/folder from diffrent branch

```bash
git checkout <branch_name> -- <paths>
```

To get package.json from dev branch to current branch:

```bash
git checkout dev -- package.json
```

## Commit current changes to different (existing )branch

```bash
git stash
git checkout other-branch
git stash pop
```

The first stash hides away your changes (basically making a temporary commit), and the subsequent stash pop re-applies them.

## Commit current changes to new branch

```bash
git stash
git checkout -b new-branch
git stash pop
```

## Remove folder from entire git history

```bash
git filter-branch -f --tree-filter "rm -rf FOLDERNAME" --prune-empty HEAD
git for-each-ref --format="%(refname)" refs/original/ | xargs -n 1 git update-ref -d
echo FOLDERNAME/ >> .gitignore
git add .gitignore
git commit -m "Removing FOLDERNAME from git history"
git gc
git push origin master --force
```

## Sign commits by default

```bash
git config --global user.signingkey <YOUR_SIGNING_KEY>
git config --global commit.gpgsign true
git config --global gpg.program gpg
```
