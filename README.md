# Git Commands

Rarely used often forgot.

¯\_(ツ)_/¯

## Tagging

> git tag -a v1.4 -m "my version 1.4"

Push the tag to the repository

> git push origin master --tags

## Remove a Tag

> git tag --delete tagname

And

> git push origin master --tags

Or

> git push --delete origin tagname

## Tagging After you have pushed

If you forgot to tag a changeset and people are all :-$ you can find that changeset and push a tag to the changeset.

> git tag -a v1.2 9fceb02

## Print Pretty Sorted List of Tags

> git log --tags --simplify-by-decoration --pretty="format:%ai %d"

```bash
$ 2018-04-23 16:13:18 -0500  (tag: 6.3.9)
$ 2018-04-20 22:24:24 -0500  (tag: 6.3.8)
```

> git log --tags --simplify-by-decoration --pretty="format:%d %cD"

```bash
 (tag: 4.0) Thu, 7 Jan 2016 23:34:57 +0600
 (tag: 3.0) Thu, 8 Oct 2015 16:49:08 +0400
```

Additional formats for testing

```git

git for-each-ref --format '%(tag)'
git for-each-ref --sort=taggerdate --format '%(tag)'
git for-each-ref --sort=-taggerdate --format '%(tag)'
git for-each-ref --sort=taggerdate --format '%(tag) %(taggerdate:raw) %(taggername) %(subject)' refs/tags
git for-each-ref --sort=taggerdate --format '%(refname) %(taggerdate)' refs/tags

```

From twitterverse - https://twitter.com/_rsc/status/1004020768840220672

> git for-each-ref --format='%(if)%(committerdate)%(then)%(committerdate)%(else)%(*committerdate)%(end) %(refname:lstrip=2)' refs/tags/*

## Clone to a folder from a tag

Quick Clone to Folder of your own name and then cd into the foler.

```git

  git clone https://github/craignicholson/myapp.git MyApp ; cd .\MyApp\; git checkout tags/3.2.9 ; cd ..

```

## Windows and CRFL or ^M and other crud

```bash
$ git config --global core.autocrlf true

# And then convert your files:

# Remove everything from the index
$ git rm --cached -r .

# Re-add all the deleted files to the index
# You should get lots of messages like: "warning: CRLF will be replaced by LF in <file>."
git diff --cached --name-only -z | xargs -0 git add

# Commit
git commit -m "Fix CRLF"

```

## Changesets

Add info about where the get the changset from Kiln.
