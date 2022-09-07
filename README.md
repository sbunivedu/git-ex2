# Git Exercise 2
For this task, you will work in a small group - between 2 and 4 people.
## Task 1
1. First, one person in the group should create an empty (**Do not** initialize the repository with a README) public repository (repo) using the person's github account.
1. This same person should then follow the instructions from github to add this github repo as a **remote** to a local repo, and push the local repo to the remote repo. Do not forget the `–u` flag, as suggested by github!
For example, the following commands push an existing repository, `lubaochuan/test.git`, from the command line:
```
git remote add origin git@github.com:lubaochuan/test.git
git push -u origin master
```
1. All of the other members of the group should then be added as collaborators, so they can commit to the repo also.
1. Next, everyone else in the group should clone the repo from github. Verify that the context of the repo is what is expected.
1. One of the group members who just cloned should now make a local commit, then push it. Everyone should verify that when they `git pull`, that commit is added to their local repo (use `git log` to check for it).
1. Look at each other’s `git log` output. Notice how the SHA-1 is the same for a given commit across every copy of the repo. Why is this important?
1. Two members of the group should now make a commit locally, and race to push it. To keep things simple, be sure to edit different files. What happens to the runner-up?
1. The runner-up should now pull. As a group, look at the output of the command.
Additionally, look at the git log, and notice that there is a **merge commit**. You may also wish to view the history graph with `git log --pretty=format:"%h %s" --graph`.
1. Repeat the last two steps a couple of times, to practice.

## Stretch Task
1. Now create a situation where two group members both edit the same line in the same file and commit it locally. Race to push.
1. When the runner-up does a pull, they should get a merge conflict.
1. Look as a group at the file in conflict, and resolve it.
1. Use the add command to stage the fix, and then use commit to make the merge commit.
Notice how this procedure is exactly the one you got used to when resolving conflicts in branches.

## Task 2
1. Make a commit, and make a silly typo in the commit message.
1. Use the `--amend` flag to enable you to fix the commit message.
1. Look at the log and notice how the mistake is magically gone.
1. Now make a commit where you make a typo in one of the files. Once again, use `--amend` to magic away your problems.
1. Create a branch. Make a commit.
1. Now switch back to your master branch. Make a (non-conflicting) commit there also.
1. Now switch back to your branch.
1. Use the `git rebase` command in your branch. Look at the history graph with `git log --pretty=format:"%h %s" --graph`, and note that you have
the commit from the master branch, but no merge commit.
1. Make one more commit in your branch.
1. Return to master. Merge your branch. Notice how, thanks to the rebase, this is a fast forward merge.

## Stretch Task
1. Find somebody from your team from the previous exercise. Have them push a commit to the central repository.
1. Make a commit locally yourself also. Note that you should not have pulled their commit at this point.
1. Try to push, and watch it fail.
1. Now, pull but using the `--rebase` flag.
1. Use git log and use `git log --pretty=format:"%h %s" --graph` to verify that there is no merge commit, and the history graph is linear.
1. Notice that your commit is the latest one, even though temporally the other member of your team made their commit afterwards. Why is this?
