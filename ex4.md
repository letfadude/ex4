# Backup

## For this exercise, create a new repository with 2 branches, dev and main/master. You continue to "develop" the dev branch with 2 commits. Now back up the repository by copying the entire directory.

```bash
mkdir repo4
cd repo4
git init
echo "Why not" > README.md
git add README.md
git commit -m "Initial commit"
git checkout -b dev
echo "featA" > a.txt
git add a.txt
git commit -m "Add a.txt"
echo "featB" > b.txt
git add b.txt
git commit -m "Add b.txt"

cd ..
cp -r repo4 repo4_backup

```

# Short Story

## Assuming you are now done with version V1.0.0 in the dev branch and want to create a straight, short main/master history (2 commits, no branches). What commands do you need to set the dev branch to the main/master branch? Which command is needed to truncate all commits for the last development to the current version to one commit?

```bash
cd repo4
git checkout main
git merge --squash dev
git commit -m "V1.0.0"

```

```plaintext
Squash commit -- not updating HEAD
 a.txt | 1 +
 b.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 a.txt
 create mode 100644 b.txt
[main 4329f10] V1.0.0
 2 files changed, 2 insertions(+)
 create mode 100644 a.txt
 create mode 100644 b.txt
```

# Tag this

## Now tag the new version as V1.0.0. What command do you use for this?

```bash
git tag V1.0.0
```

# Local and remote

# Start again from 1. - but this time with a cloned remote repository. Describe your experience. How does local development differ from development with a remote repository?

```bash
cd ..
rm -rf *
echo "# ex4" >> README.md
git init
git add README.md
git commit -m "first commit"
# -M  Shortcut for --move --force.
git branch -M main
git remote add origin git@github.com:letfadude/ex4.git
git push -u origin main
# dev setup
git checkout -b dev
echo "featA" > a.txt
git add a.txt
git commit -m "Add a.txt"
echo "featB" > b.txt
git add b.txt
git commit -m "Add b.txt"
# PUSH !!!
git push -u origin dev
# backup
cd ..
cp -r repo4 repo4_backup

```

# Add and Set

# Copy the backup repository to a new directory and continue working in it. Switch to dev branch and create 3 new versions, in each version create a new file, e.g. a.txt, b.txt, c.txt - i.e. in each new version a new file has been added. Switch to the main/master branch and get the commit where b.txt was added and set it to main/master. What commands do you use, what options are there, and what specifically do they do? (SHA1 of the commit, directory)

# Patch

# Create a patch of the latest commit and email it to a selected git friend from your association. What commands do you use?

# Not ready to commit

# Using your repository backup from Task 1, modify a file on the dev branch and add a new file. Now you need to perform a quick hotfix on the main/master branch, but your changes to the dev branch are not yet complete and cannot yet be committed. Save your changes with a meaningful info text. What commands do you need to do this?

# Restore

# After completing the hotfix on the main/master branch, you want to restore your cached changes to the dev branch and then clear the cache. What are your options for doing this?

# Who was that?

# In the course of testing, you have discovered an error and want to contact the author of the affected line in the code to find out why the change was made. What options do you have with git to quickly get the information you need? What options can be used to specify the information output?

# Project Management

# The project management of your project wants all commits to refer to the request from the issue tracking system in the future. Therefore the commit messages should always start with the reference of the ticket. The ticket ID is structured as follows: "KFMG-<consecutive number from 0001 - 9999>". You should ensure that the commit messages conform to the required format. How do you implement this requirement with Git?

```

```

```

```
