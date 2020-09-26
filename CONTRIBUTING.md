# Contribution Overview
Please do! Thanks for your help in improving projects for AstroSonic! :rocket:

All contributors are welcome. Not sure where to start? Please see the [Issues page](https://initiative.astrosonic.tech) to check for open issues on. This project is community-built and welcomes collaboration. Contributors are expected to adhere to our [Code of Conduct](CODE_OF_CONDUCT.md).

All set to contribute? Grab an open issue with the [help-wanted label](../../labels/help%20wanted) and jump in. Join our [Discord channel](bit.ly/astrosonic-discord) and engage in conversation. Create a [new issue](/../../issues/new/choose) if needed.  All [pull requests](/../../pulls) should ideally reference an open [issue](/../../issues). Include keywords in your pull request descriptions, as well as commit messages, to [automatically close related issues in GitHub](https://help.github.com/en/github/managing-your-work-on-github/closing-issues-using-keywords).

# How to start contributing
Just head over to the GitHub page and click the "Fork" button. It's just that simple. Once you've done that, you can use your favorite git client to clone your repo or just head straight to the command line:

## Clone your fork to your local machine
```
git clone git@github.com:USERNAME/FORKED-PROJECT.git
```
Keeping Your Fork Up to Date
While this isn't a necessary step, if you plan on doing anything more than a tiny quick fix, you'll want to make sure you keep your fork up to date by tracking the original "upstream" repo that you forked earlier. To do this, you'll need to add a remote:

## Add 'upstream' repo to list of remotes
```
git remote add upstream https://github.com/astrosonic/initiative.git
``` 
("Initiative" is used as the example repo. Be sure to reference the _actual_ repo you're contributing to e.g. "sanctuary").

## Verify the new remote named 'upstream'
```
git remote -v
```
Whenever you want to update your fork with the latest upstream changes, you'll need to first fetch the upstream repo's branches and latest commits to bring them into your repository:

## Fetch from upstream remote
```
git fetch upstream
```

## View all branches, including those from upstream
```
git branch -va
```
Now, checkout your master branch and merge the upstream repo's master branch:

## Checkout your master branch and merge upstream
```
git checkout master
git merge upstream/master
```
If there are no unique commits on the local master branch, git will simply perform a fast-forward. However, if you have been making changes on master (in the vast majority of cases you probably shouldn't be - see the next section, you may have to deal with conflicts. When doing so, be careful to respect the changes made upstream.

Now, your local master branch is up-to-date with everything modified upstream.

**Create a Branch** (doing your work)
Whenever you begin work on a new feature or bugfix, it's important that you create a new branch. Not only is it proper git workflow, but it also keeps your changes organized and separated from the master branch so that you can easily submit and manage multiple pull requests for every task you complete.

To create a new branch and start working on it, perform the following flow.

## Check out the master branch - you want your new branch to come from the master
```
git checkout master
```

## Create a new branch (give your branch its own simple informative name)
For enhancements use `feature/your_username/issue#` or `feature/your_username/name_of_feature`

For bugs use `bug/your_username/issue#` or `bug/your_username/name_of_bug`

```
git branch feature/jdoe/567
```

## Switch to your new branch
```
git checkout feature/jdoe/567
```
Now, go to town hacking away and making whatever changes you want to.

## Submitting your changes (a Pull Request)
Before submitting your pull request, you might want to do a few things to clean up your branch and make it as simple as possible for the original repo's maintainer to test, accept, and merge your work.

In the time that you've been working on your changes, if any commits have been made to the upstream master branch, you will need to rebase your development branch so that merging it will be a simple fast-forward that won't require any conflict resolution work.

## Signing off your commits.

You simply add a line to each of your git commit messages to sign off your commits:


```
Signed-off-by: Jane Smith <jane.smith@example.com>
```

In most cases, you can add this signoff to your commit automatically with the
`-s` or `--signoff` flag to `git commit`. You must use your real name and a reachable email
address (sorry, no pseudonyms or anonymous contributions). An example of signing off on a commit:
```
$ commit -s -m “my commit message w/signoff”
```

To ensure all your commits are signed, you may choose to add this alias to your global ```.gitconfig```:

*~/.gitconfig*
```
[alias]
  amend = commit -s --amend
  cm = commit -s -m
  commit = commit -s
  ```

## Fetch upstream master and merge with your repo's master branch
```
git fetch upstream
git checkout master
git merge upstream/master
```

## If there were any new commits, rebase your development branch
```
git checkout feature/jdoe/567
git rebase master
```
Now, it may be desirable to squash some of your smaller commits down into a small number of larger more cohesive commits. You can do this with an interactive rebase:

## Rebase all commits on your development branch
```
git checkout
git rebase -i master
```
This will open up a text editor where you can specify which commits to squash.

## Submitting
Once you've committed and pushed all of your changes to GitHub, go to the page for your fork on GitHub, select your development branch, and click the pull request button. If you need to make any adjustments to your pull request, just push the updates to GitHub. Your pull request will automatically track the changes in your development branch and update it.
