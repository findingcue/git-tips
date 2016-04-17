# Code-review process using Git

## Pull latest changes to local master branch
    (master) $ git pull origin

## Create a new branch for story (feature) you're working on
    (master) $ git checkout -b feature/masquerading

## Make changes, run tests, commit etc.
    (feature/masquerading) $ subl {filename}
    (feature/masquerading) $ git add {filename}
    (feature/masquerading) $ git commit

## Compare changes made from master
If difftool configured e.g. [SourceGear DiffMerge](https://sourcegear.com/diffmerge)

    (master) $ git difftool master..feature/masquerading

Alternatively, you can use [Atlassian SourceTree](https://www.atlassian.com/software/sourcetree)

## Push your commits to server for others to review
(feature/masquerading) $ git push -u origin feature/masquerading

## Ask for feedback (initiate pull request)
Use the Git hosting site (e.g. GitHub) to create a pull request. After incorporating reviewers' 
comments, make further commits to your branch, push your new commits to the remote. Service will 
automatically update the pull request to reflect new changes, so you do not need to issue another 
pull request. Repeat the process below until you have incorporated all the feedback and ready to
merge to master.

    (feature/masquerading) $ subl {filename}
    (feature/masquerading) $ git add {filename}
    (feature/masquerading) $ git commit
    (feature/masquerading) $ git push

## To view all commits on 'master' that aren't in your current branch
    (feature/masquerading) $ git log ..master

If you see any commits here (as a result of above command), then rebase the feature branch using following command.
This replays your commits on top of the new commits from the destination branch so that the merge can be a 'fast-forward.

    (feature/masquerading) $ git rebase master

## Merge feature work from local-branch to local-master 
One option is to merge pull-request from the service-site, which will trigger code merge. 

Alternatively, you can use git command 'merge --squash' that squashes all the commits into one commit, which is 
recommended because these commits are likely to achieve the same goal. If you go with "merge --squash", you need 
an extra "git commit".

    (feature/masquerading) $ git checkout master
    (master) $ git merge --squash feature/masquerading

Now that changes are in local (master) branch , we need to commit and push to remote (master) repo

    $ git add {filename}
    $ git commit
    $ git push origin

## Delete the local and remote feature branches

    (master) $ git branch -D feature/masquerading
    (master) $ git push origin :feature/masquerading
