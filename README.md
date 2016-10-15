# Git Practice

### Undo commit
* To change the last commit message use `--amend`
```bash
$ git commit --amend -m "New commit message"

// Open editor to edit the message
git commit --amend
```

* To undo commit 
```bash
$ git commit -m "Something terribly misguided"              (1)
$ git reset HEAD~                                           (2)
<< edit files as necessary >>                               (3)
$ git add ...                                               (4)
$ git commit -c ORIG_HEAD                                   (5)
```

1. This is what you want to undo
2. This leaves your working tree (the state of your files on disk) unchanged but undoes the commit and leaves the changes you committed unstaged (so they'll appear as "Changes not staged for commit" in `git status` and you'll need to add them again before committing). If you only want to add more changes to the previous commit, or change the commit message, you could use `git reset --soft HEAD~` instead, which is like `git reset HEAD~` but leaves your existing changes staged.
3. Make corrections to working tree files.
4. `git add` anything that you want to include in your new commit.
5. Commit the changes, reusing the old commit message. `reset` copied the old head to `.git/ORIG_HEAD`; commit with `-c ORIG_HEAD` will open an editor, which initially contains the log message from the old commit and allows you to edit it. If you do not need to edit the message, you could use the `-C` option.

### Push tags to git server
```bash
// To push single tag
$ git push origin <tag_name>

// To push all tags
$ git push --tags
```
### Branch

#### Show all branch
`$ git branch -a`

#### Show remote branch
`$ git branch -r`

#### Create new Branch
`$ git branch <branch_name>`

#### Switch branch
`$ git checkout <branch_name>`

#### Create new and checkout
`$ git checkout -b <branch_name>`

#### Delete branch 
`$ git branch -d <branch_name>`

#### Pull from branch
`$ git pull <remote_name> <branch_name>`

#### Push branch to remote
`$ git push <remote_name> <branch_name>`



