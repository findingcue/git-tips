# Code Review using Git
GIT Code review process (should be followed for every new feature)

## Create a new branch for the current story (feature) you're working on:
_(master) $ git checkout -b feature/masquerading_

## Make changes, run tests, commit etc.
_(feature/masquerading) $ subl {filename}_

_(feature/masquerading) $ git add {filename}_

_(feature/masquerading) $ git commit_

## Compare changes made from master branch
_(master) $ git difftool master..feature/masquerading_

## Push your commits to the remote for others to review
(feature/masquerading) $ git push -u origin feature/masquerading

## Ask for feedback
Use the Github/VisualStudio site to create a pull request. After digesting reviewers' comments, make further commits to your branch, push your new commits to the remote.
GitHub will automatically update the pull request to contain your new changes, so you do not need to issue another pull request.

_(feature/masquerading) $ subl {filename}_

_(feature/masquerading) $ git add {filename}_

_(feature/masquerading) $ git commit_

_(feature/masquerading) $ git push_

## This shows all commits on 'master' that aren't in your current branch history.
_(feature/masquerading) $ git log ..master_

If you see any commits here (as a result of above command), then rebase the feature branch using following command.
This replays your commits on top of the new commits from the destination branch so that the merge can be a 'fast-forward.

_(feature/masquerading) $ git rebase master_

Merge feature work from local branch to master. 'merge --squash' squashes all the commits into 
one commit, which is recommended because these commits most likely achieve the same goal. If you go 
with "merge --squash", you need an extra "git commit" and modifying the commit message.

_ (feature/masquerading) $ git checkout master_

_(master) $ git merge --squash feature/masquerading_

_(master) $ git add {filename}_

_(master) $ git commit_

Now delete the local and remote feature branches:

_(master) $ git branch -D feature/masquerading_

_(master) $ git push origin :feature/masquerading_

Now that changes are in local-master branch, we need to commit and push to remote-master repo.

_$ git add {filename}_

_$ git commit_

_$ git push origin_
