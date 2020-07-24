git branch
see all local branches you have for a repo and see which you are CURRENTLY on
git checkout
checkout an existing branch
git checkout -b branch-name
create a new branch with “branch-name” from current branch
git add --all
stage all changed files
git commit -m
commit all staged files and write a description of what the commit does
git push
push commits to origin branch (follow directions first time to create origin branch on github)
git branch -m
renames a branch, best if done before pushing branch to origin (which creates a branch copy on github)
git rebase branch-name
moves all of your current branch’s commits on top of “branch-name”, good for when your main branch (e.g. “develop”) has new changes from a coworker, but you’re still developing, so you rebase on the updated “develop” (make your own commits first). This is cleaner for dev history then merging, but can require fixing conflicts
git stash
save your un-committed changes from current branch to an array of stashes (good for temporarily saving your un-ready changes if you need to switch branches to work on something else or realize you started on “master” or “develop” main branches and need to create a clean branch first!)
git stash pop
apply the most recent stash of code changes to your current branch
git stash list
see the array of stashed changes
git stash apply stash@{n}
if you stashed a few things and have an array, n is the index of the stash you will apply
git status
see what files are modified, what files are staged, etc.
git diff
review your file changes in the terminal before you stage and commit (make sure you didn’t forget any temporary changes, etc.)
git log
see the history of commits of current branch which also shows commit hashes
git reset
un-stage your un-committed changes on current branch
git reset --hard
un-stage and DELETE any un-committed changes on current branch
git reset --hard commit-hash
delete all commits and un-staged changes on current branch, resetting the branch back to “commit-hash” commit (commit hash in this command is some long identifier like 23x323b3n2mkf45…). This will make it like your changes never happened.
git revert commit-hash
makes a NEW commit that undoes the changes going back to code status at “commit-hash”. Use this when you want to keep a record on the branch that you’re undoing previous changes.
git cherry-pick commit-hash
when you have a commit-hash for a change on another branch you want to copy over to your current branch, you can use this command. So for example, let’s say you made 3 commits to the wrong branch before realizing. You cherry-pick three times to get those changes on the desired branch then reset/revert that first branch.
