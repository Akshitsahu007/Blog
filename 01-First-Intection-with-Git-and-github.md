# What is Git?

Git is a distributed (virsion controling system) that helps devlopers track changes, Collborate, with team members, and mange different virsion of a projact

# What is Git?

Github was cloud-base platform that host Git repositories, making it easy to collaborate, reviwe code, and manage projeact details

## Why Git became popular

Before Git, devlopers mainlly use virsion controle system such as CVS and SVN. there system stored chnages diffrence and relied on centralized model, git introduced a snapshort-based approch that make vision controle faster and more flexible.

## How Git works

git store each commit as snapshot of the projact. internally, it effcienly reuses unchanged data, making it both fast and space-efficient

## Git Core Terminologies and Commends

- Head
- index / Staging Area
- Repository (Repo)
- Working Directory
- commit
- pull
- fatch
- push
- clone
- Fork
- Branch
- Checkout
- Remote
- origin
- Request
- Merge

### git Head

Head is special reference Git.
It points to your current branch or latest commit you're currently working on.
Whenever you create a new commit, HEAD automatically moves to that commit.

```shell
git show HEAD
```

or

```shell
git branch --show-current
```

### Index / Staging Area

'git index' aera bettwen you local working floder and your commit aera , alos know is git staging area

### Repository (Repo)

git Repository (sort form is repo) is a vitual storge space where in this .git floder
where all file track there two types repo local or remote

**Local Repository** - local floder that exist in your computer or local machine

**Remote Repository** - remote repo is stoge on you remote server floder

### Working Directory

Working Directory floder in your computer where you creating, edit, deleted projact file before staging and committing them

### git Commit

A commit creates a snapsort of your projact's current state. Each commit records the chnages you're made along with massage describing those chnages.

```
git commit -m "chnages in login servies"
```

### git Pull

git pull donwlode and marge the chnages from Remort Repository to Local Repository

```
git pull -all

git pull -rebase
```

### Git fatch

git fetch download changes form remort repo in local to allow diff

```
git fetch origin

git diff main origin/main

// if all okay so run

git merge origin/main

```

### push

git push uplode you local commit into remort Repo

```
git push origin
```

### git request

git request is also know is pull reuest for marge chnage into remort branch

```
git checkout -b feature-branch-name

git add .

git commit -m "Describe your changes clearly"

git push origin feature-branch-name
```

### git merge

git marge is marge other comiit in the repo

```
git merge feature-branch

```

## summarize

in this article we learned what git and github are why Git became polular and the basic git terminology use in daily devlopment. understanding concepts like repositories, commit,branches, and staging area.
