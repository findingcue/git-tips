## To pull repository first-time on local-machine
	$ git clone git@github.com:findingcue/git-tips.git

## To see what are the pending changes (waiting to commit)
	$ git status

## To see the history of check-in
	$ git log

## Add pending changes (from local directory)
	$ git add .

## To commit changes to local-repository
	$ git commit

## To pull new changes made to repository
	$ git pull git@github.com:findingcue/git-tips.git

## To push new changes to GITHUB server
	$ git push git@github.com:findingcue/git-tips.git

## Do a dry run to see what will be added as a result of 'git add'
	$ git add -n .

## To rename a file
	$ git mv {old-file-name} {new-file-name}

## If above doesn't work then try the following sequence which is really what 'git mv' internally does
	$ mv {old-file-name} {new-file-name}
	$ git rm {old-file-name}
	$ git add {new-file-name}

## To remove file from changes-not-staged-for-commit
	$ git checkout -- {filename}

## To remove a file from changes-to-be-committed (cached index):
	$ git reset {file-name}

## Show all git remote branches and the corresponding url-targets
	$ git remote -v

## Show all git remote branches
	$ git remote show

## Git remote show {remote-branch-name}
	$ git remote show origin
	$ git remote show upstream

## Pulls in changes not present in your local repository, without modifying your files
	$ git fetch {branch-name} e.g. git fetch upstream

## To stash current working changes, pull latest server changes, and then apply back the stashed changes
	$ git stash
	$ git pull origin
	$ git stash apply
