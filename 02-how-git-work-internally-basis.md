# How Git work internally Basic

As devloper we mosstly use git commend like `git add`, `git commit` , `git checkout -b new-branch`. but what achully happens when we run this commends.

undrastading git intranal it's help you understnding git work and resones behinding the bugs.

In this article, we will explore

1. Git’s Data Model
2. What inside the `.git` folder
3. How `get commit` work
4. How `git checkout -b new-branch` work
5. summary

# Git's Data model

At the root, git is **content-addressable filesystem**. It's stores data as objact, and each objact contain unique SH hash

when You add file, git genrate 40 chreacter hexadecimal SHA-1 hash of the file's contents. this hash is unique identifier in databess

```
File contents: "Hello, World!"
SHA-1 hash:    5dd01c177f5d7d1be5346a5bc18a569a7410c2ef
```

same content allways produce same hash. so two file identicl content same (even it's different name) they share same hash

git Store content once and point multiple files, which store ifective even accross thousands of commit.

Git every thights in a objact. there are four type of objact but three are main objacts tree, blob and commit.

![](https://substackcdn.com/image/fetch/$s_!oPmT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fab6671e3-08ed-4090-9ea8-ef979856d07f_1662x1594.png)

# What inside the `.git` folder

when you git init git create folder inside your projact folder

this are this flolder and file we get on git folder

```
.git/
├── HEAD              (contains: ref: refs/heads/main)
├── config            (repository configuration)
├── description       (used by GitWeb, rarely relevant)
├── hooks/            (scripts triggered by Git events)
├── info/             (exclude patterns, other info)
├── objects/          (the object database, initially empty)
│   ├── info/
│   └── pack/
└── refs/             (references to commits)
    ├── heads/        (branch pointers, initially empty)
    └── tags/         (tag pointers)

```

All objact live inside in objact folder.

Git use simple oranizition scheme: Hash 2 prefixed are sub Folder name remening 38 chrachter are file name.

```
git/objects/
├── A4/
│   └── d01c177f5d7d1be5346a5bc18a569a7410c2ef  (blob)
├── C5/
│   └── 5f8a2b9d3e7f1a6b0c8d5e2f9a4b7c3d6e0f1a  (tree)
├── a1/
│   └── b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0  (commit)
└── ...

```

This two-charchter perfix prevent any single directory from containing too many files, which could slow down filesystem operations.

# Credit

[article](https://www.linkedin.com/pulse/visualize-how-git-works-internally-your-local-using-few-sumon-dey/)
