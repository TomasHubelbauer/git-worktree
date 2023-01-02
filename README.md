# Git Worktree

In this repository I am experimenting with the `git worktree` command.
It should allow me to check out a repository and then check out a
worktree or multiple so that I can work on multiple branches at the
same time without needing to switch branches and stash changes.

In theory I think it should work like this:

```sh
git clone …
git worktree add worktree-1-directory existing-branch
git worktree add -b new-branch worktree-2-directory
```

[Source](https://stackoverflow.com/a/45491767/2715716)

I am going to test this out by doing this:

1. Creating a new remote branch on GitHub alongside `main`
2. Cloning this repository and checking out the new branch to a worktree
3. Creating a new branch into another worktree
4. Making changes to both worktrees
5. Pushing the changes and checking the diffs against `main`
