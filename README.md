# Git Commands

Ones rarely used often forgot.

¯\_(ツ)_/¯

## Tagging

> git tag -a v1.4 -m "my version 1.4"

## Tagging After you have pushed

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

## Clone to a folder from a tag

Quick Clone to Folder of your own name and then cd into the foler.

```git

  git clone https://github/craignicholson/myapp.git MDMServicesDatabase ; cd .\MDMServicesDatabase\; git checkout tags/3.2.9 ; cd ..

```

## Changesets

Add info about where the get the changset from Kiln.