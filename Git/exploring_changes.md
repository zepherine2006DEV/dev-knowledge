# Git Hints and Tips

## Basics

* Get a good understanding of the 3 trees, and the roles they play.
  * HEAD - Last commit snapshot (and the parent of the next commit).
  * Index - Proposed next commit snapshot. Also known as staging.
  * Working Directory - Sandbox.

## git diff

By default (i.e. without any extra arguments) git diff compares the *working tree* with the *staging area* (index). This tells you what is not yet staged for commit.

```console
git diff
```

So, if changes to a tracked file have just been staged no differences will be shown.
Note that if a file is new and hasn't been added to staging, no diff will be shown. Once it's been added (and is being tracked) any subsequent changes will result in a diff.

It's also possible to check the difference between the *staging area* and the *last commit* (HEAD). This tells you what would be commited if git commit was run.

```console
git diff --cached
```

Finally, you can compare the *working tree* with the *last commit* (HEAD). This tells you what you would commit if using "git commit -a"

```
git diff HEAD
```

**Why is this useful?**

* Confirming what you're about to commit is a cohesive set of changes.