# Contributing to SET.SFDC

## Code of Conduct

## Code Contributions

Please make sure all pull requests can be tied back to a feature or bug fix.

### Step 1: Clone

Clone the repository into a new directory locally:

```shellsession
$ git clone https://github.com/CarMax/SET.CRM.git
$ cd SET.CRM
```

### Step 2: Branch

You should be on the `develop` branch by default, reate a branch and start
hacking:

```shellsession
$ git checkout -b my-branch
```

### Step 3: Commit

Make sure git knows your name and email address:

```shellsession
$ git config --global user.name "J. Random User"
$ git config --global user.email "j.random.user@example.com"
```

Add and commit:

```shellsession
$ git add my/changed/files
$ git commit
```

Writing good commit logs is important. A commit log should describe what changed
and why. Follow these guidelines when writing one:

1. The first line should be 50 characters or less and contain a short
   description of the change. All words in the description should be in
   lowercase with the exception of proper nouns, acronyms, and the ones that
   refer to code, like function/variable names. The description should
   be prefixed with the name of the changed subsystem and start with an
   imperative verb. Example: "net: add localAddress and localPort to Socket"
2. Keep the second line blank.
3. Wrap all other lines at 72 columns.

A good commit log can look something like this:

```text
subsystem: explain the commit in one line

Body of commit message is a few lines of text, explaining things
in more detail, possibly giving some background about the issue
being fixed, etc.

The body of the commit message can be several paragraphs, and
please do proper word-wrap and keep columns shorter than about
72 characters or so. That way, `git log` will show things
nicely even when it is indented.
```

The header line should be meaningful; it is what other people see when they run
`git shortlog` or `git log --oneline`.

Check the output of `git log --oneline files_that_you_changed` to find out what
subsystem (or subsystems) your changes touch.

### Step 4: Rebase

Use `git rebase` (not `git merge`) to sync your work from time to time.

```shellsession
$ git fetch origin
$ git rebase origin/develop
```

Resolve any merge conflicts.

### Step 5: Push and test

Push your code to origin.

```shellsession
$ git push origin my-branch
```

Run all available Unit Tests by using GearSet to deploy your branch to your org
before submitting a Pull Request.

### Step 6: Pull request

Click the __New pull request__ button and fill out the form, pull requests are
usually reviewed within a few days.

### Step 7: Discuss and update

You will probably get feedback or requests for changes to your Pull Request.
This is a big part of the submission process so don't be disheartened!

To make changes to an existing Pull Request, make the changes to your branch.
When you push that branch to your fork, GitHub will automatically update the
Pull Request.

You can push more commits to your branch:

```shellsession
$ git add my/changed/files
$ git commit
$ git push origin my-branch
```

Or you can rebase against develop:

```shellsession
$ git fetch --all
$ git rebase origin/develop
$ git push origin my-branch
```

### Step 8: Continuous Integration

Once your code has been reviewed and approved, it will be merged into the
`develop` branch where a Continuous Integration task will notice the new code
and deploy it to our integration environment.

### Step 9: Release

A `release` branch will be created once we believe the `develop` branch is
stable. This release branch will be deployed to our QA environment where
regression testing take place. Once we get the thumbs up, we will merge the
release branch into `master` and tag it with a release number. 
