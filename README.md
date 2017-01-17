# git-tips
List of handy git commands for dayli usage

To Be Formatted

git add -p
Rather than git add everything or individual files, this -p will allow you to step through each change, or hunk, and decide if you’d like to commit it. This is really handy if you have made two different changes to the same file and want to commit them separately.

git log -5 --pretty --oneline
View your last 5 latest commits each on their own line.


git shortlog -sn
Quickly get a list of contributors and see how many commits each person has.


git log --all --graph --decorate --oneline --simplify-by-decoration
This one is the best – you need to see what it does visually

You’ll never remember this one so put it in your ~/.gitconfig file under [alias]

wow = log --all --graph --decorate --oneline --simplify-by-decoration

git checkout pr/123
Quickly check out a remote for pull request review. You’ll need to set it up like this.


git diff --shortstat "@{0 day ago}"
See how many lines of code you have written today.


git checkout -
It’s like the jump button on your TV remote – jump back to to your last branch.

git reset --soft HEAD~3
A soft reset will keep your changes but allow you to “uncommit” something.

Instead of doing a squash, Dan prefers to dial back HEAD any number of commits and then add & commit everything into a single commit.


git reflog
David says it best — “Don’t worry, it’s probably saved somewhere”. Git reflog allows you to see every step you have made with git allowing you to retract and reinstate your steps.


git stash, then git stash pop
Stash let’s you squirrel away unstaged changes, do some work, and then apply those changes back on.

git stash will stash those changes and put them into your list — I like to think of this as an array of changes. Now to get them back you can git stash apply but what Sam is suggesting here is that you use git stash pop instead which will also bring back your changes, but it removes them from your stash “array”.
ok

git log -S puppy
Search the commit history for the word puppy and display matching commits.

git latest = for-each-ref --count=30 --sort=-committerdate refs/heads/ --format='%(refname:short)’
Allows you to view your latest branchces – this is helpful for when your branch names are based on bug IDs that you have a hard time remembering.

git config --global help.autocorrect -1
Mistype or misspell a git command? Immediately re-run the correct command. You can use -1 to 1000 to wait a full second before the command is re-run.

git commit --amend
Great for squashing staged files into your last commit.

git cherry-pick [hash]
As long as the commit has been fetched somewhere, you can cherry pick that code in your own branch without having to merge the entire thing.

git remote update --prune
Remove local branches that have been deleted from your remote (like GitHub). You can always run git remote prune origin --dry-run to see what will be deleted before going all in.

git rebase -i HEAD~4

Interactive rebase allows you to pick and choose which commits you can pick, squash, reword, edit, or fixup
