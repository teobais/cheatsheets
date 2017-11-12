show local branches: git branch
delete a branch: git branch -D [branch_name]
Cloning a repo from someone else's Github and pushing it to a repo on my Github: git remote set-url origin http://github.com/YOU/YOUR_REPO
Push a new local branch to a remote Git repository and track it too: git checkout -b <branch>   ,   git push -u origin <branch>
Easily keep gh-pages in sync with master : http://lea.verou.me/2011/10/easily-keep-gh-pages-in-sync-with-master/
Revert a locally modified file: git checkout -- [filename]
Diff 2 branches : git diff --stat --color master..branchName
commit only part of a file: git add --patch filename

rename (locally & remotely) a branch: 
1. switch to branch which needs to be renamed
2. git branch -m <new_name>
3. git push origin :<old_name>
4. git push origin <new_name>:refs/heads/<new_name>
---

Diff current branch with a stash: git stash show -p stash@{1}
Undo a local commit: git reset HEAD~1

Diff specific file among two different branches
```git diff feature-branch master -- pom.xml```

Checkout tag and branch it
```git checkout tags/<tag_name> -b <branch_name>```

Create branch from specific hash
```git branch branchname <sha1-of-commit>```

Execute `git status` on directory `B`
```git -C B log```

Overwrite single file in feature branch with the same file in the master branch
`git checkout FROM_BRANCH_NAME path/to/file`

### Rename a local and remote branch in git
- When on the branch you want to rename `git branch -m new-name`
- If on a different branch `git branch -m old-name new-name`
- Delete the old-name remote branch and push the new-name local branch `git push origin :old-name new-name`
- Reset the upstream branch for the new-name local branch `git push origin -u new-name`

### Create an annotated tag
```
git tag -a v1.4 -m 'my version 1.4'
git push origin --tags
```

### Sync a fork
```
git fetch upstream
git checkout master
git merge upstream/master
```

### Rebase specific commit from a different upstream
```
git rebase --onto master [commit SHA-1] upstream/master
```
If it is about a merge commit , you will probably get into a Detached HEAD state, which means that you'd better force push.

#### Forcing a push from a Detached HEAD
If you force a push from a Detached HEAD to a specific branch, apparently you first have to checkout that specific branch and pull, in order for the changes to also be applied locally.

### Cherry-picking a merge commit
A merge commit is a result of 2 separate commits, so, cherry-pick command needs a bit of guidance here:
```
git cherry-pick 47c2931e0919ecafeaaf1b33839dede64dd33ba4
error: commit 47c2931e0919ecafeaaf1b33839dede64dd33ba4 is a merge but no -m option was given.
fatal: cherry-pick failed
```
As [`-m`](https://stackoverflow.com/questions/24301390/git-revert-hash-not-allowed-due-to-a-merge-but-no-m-option-was-given) you have to specify the parent on which the cherry-pick will be based.

```
git cherry-pick 47c2931e0919ecafeaaf1b33839dede64dd33ba4 -m 1
```

Indexing for the `-m` option applies to the order in which the commits appear visually. So, in the following line, `-m 1` corresponds to `e391102`

```
2 parents e391102 + 3d399d9 commit 47c2931e0919ecafeaaf1b33839dede64dd33ba4
```
