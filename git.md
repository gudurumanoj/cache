## GIT

Using git clone with the --depth option. When you use --depth 1 , you're **telling Git to only fetch the latest commit**. --depth 1 is the most commonly used depth. It means you are cloning the repository with only the latest commit of the main branch


### Commands
```bash
git branch -a                   ## lists all branches
git checkout <branch_name>      ## changes the branch to <branch_name>
git config user.name            ## to get the username of the git configured git account
git status
git add <file1> <file2> ...
git commit -m "<message>"
git push origin <branch_name>

git push https://guduru-manoj:<token>@github.com/<branch>/folder.git  ## to push with a specific token

git push https://guduru-manoj:<token>@github.com/<branch>/path/to/dir/folder.git  ## to push with a specific token
```

### Committing to a repo that's ahead and resolving conflicts
### Using Rebase
`git rebase` rewrites local commits **on top of** the latest commits from the remote branch. It creates a **linear history** by moving local work to follow the remote work
```bash
Before rebase:
remote:     A---B---C (origin/<branch>)
local:             \--D---E (local commits)

After rebase:
rebased:   A---B---C---D'---E' (local commits reapplied)

```
Before rebasing, it's always essential to commit/stash your changes (`stash` is like a temporary place to store your uncommitted changes without committing them). To keep it simple, let's just commit the changes
```bash

git fetch origin/<branchname>       ## to fetch the changes from the branch which is ahead

git rebase origin/<branch-name>    ## to merge the changes in remote file, can result in conflicts which are supposed to be resolved manually in all files. It's just text based where the text should be deleted. These conflict files would be informed to you by git while it tries rebasing

	git add <file>       ## Once you fix the changes, you need to add the file change and continue rebasing
	
	git rebase --continue

git push origin <branch-name> --force-with-lease    ## push the changes once rebasing is done. --force-with-lease aborts the push if someone one else has made the changes on the remote branch

```

