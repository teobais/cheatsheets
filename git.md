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


