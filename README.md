# Git Commands

Rarely used often forgot.

¯\_(ツ)_/¯

## Tagging

> git tag -a v1.4 -m "my version 1.4"

Push the tag to the repository

> git push origin master --tags

## Remove a Tag

> git tag --delete tagname
> git push origin master --tags

or

> git push --delete origin tagname

## Tagging After you have pushed

If you forgot to tag a changeset and people are all :-$ you can find that changeset and push a tag to the changeset.

> git tag -a v1.2 9fceb02

## Print Pretty Sorted List of Tags

> git log --tags --simplify-by-decoration --pretty="format:%ai %d"

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

  git clone https://github/craignicholson/myapp.git MDMServicesDatabase ; cd .\MDMServicesDatabase\; git checkout tags/3.2.9 ; cd ..

```

## Changesets

Add info about where the get the changset from Kiln.