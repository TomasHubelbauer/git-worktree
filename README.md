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

- [x] Creating a new remote branch on GitHub alongside `main`
  https://github.com/TomasHubelbauer/git-worktree/tree/tom-test
- [x] Cloning this repository and checking a the new branch to a worktree
  ```sh
  git worktree add -b tom-test-2 worktree1
  cd worktree1
  git status
  # On branch tom-test-2
  cd ..
  git status
  # On branch main …
  ```
- [x] Making changes to the new local branch worktree and pushing them
  ```sh
  touch test-in-worktree-1
  git add *
  git commit -m "Add the test file" -m "This is a test of adding a change in a worktree"
  git push --set-upstream origin tom-test-2
  ```
  https://github.com/TomasHubelbauer/git-worktree/tree/tom-test-2
- [ ] Checking out the `tom-test` existing remote branch to a worktree
- [ ] Making changes to the existing remote branch worktree and pushing them
- [ ] Pushing the changes and checking the diffs against `main`

## Fun facts

- You probably want to ignore the worktree directory otherwise it will
  show up as a change in `git status` in its parent directory chain
