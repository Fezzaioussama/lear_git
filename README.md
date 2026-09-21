# lear_git

> A scratch repository for practising git — branching, committing, merging. Not a project.

The files here are placeholders that existed to have something to commit. The
repository is the exercise; the contents aren't meant to do anything.

```
index.html      # empty
main.css        # empty
index.js        # one line
test/test.js
.index.js.swp   # ⚠ committed Vim swap file — should be removed and gitignored
```

## Housekeeping

`.index.js.swp` is a Vim swap file that got committed by accident. To clean it
up:

```bash
git rm --cached .index.js.swp
printf '*.swp\n*.swo\n' >> .gitignore
git commit -m "Remove committed Vim swap file"
```

## Git reference

The commands this repo was created to practise:

```bash
git init                      # start a repository
git status                    # what's changed
git add <file>                # stage changes
git commit -m "message"       # record them
git log --oneline --graph     # view history

git branch <name>             # create a branch
git switch <name>             # move to it
git switch -c <name>          # create and move in one step
git merge <name>              # merge it back

git remote add origin <url>   # connect a remote
git push -u origin main       # first push
git pull                      # fetch and merge
```

Undoing things, which is the part worth actually practising:

```bash
git restore <file>            # discard uncommitted changes to a file
git restore --staged <file>   # unstage, keep the changes
git commit --amend            # fix the last commit
git revert <commit>           # new commit undoing an old one (safe on shared branches)
git reset --hard <commit>     # move the branch, discard everything after (destructive)
```
