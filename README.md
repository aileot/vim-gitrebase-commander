# Gitrebase Commander

## Installation

Use your favorite plugin manager

### For dein

```vim
call dein#add('kaile256/vim-gitrebase-commander')
```

or in toml,

```toml
[[plugins]]
repo = 'kaile256/vim-gitrebase-commander'
```

## Usage

### Default mappings

```vim
let g:gitrebase_commander#prefix = 'z'
let g:gitrebase_commander#suffixes = {
      \ 'p': 'pick',
      \ 'r': 'reword',
      \ 'e': 'edit',
      \ 's': 'squash',
      \ 'f': 'fixup',
      \ 'x': 'exec',
      \ 'b': 'break',
      \ 'd': 'drop',
      \ 'l': 'label',
      \ 't': 'reset',
      \ 'm': 'merge',
      \ }
```

### Excerpt from a gitrebase file

```gitrebase
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
```

### Excuse about default prefix `z`

Do you use these default mappings while editing gitrebase?

- `zr` to reduce fold
- `zf` to create fold
- `zx` to update fold
- `zd` to delete fold
- `zm` to fold more

- `zs`, `ze` or `zl` to scroll horizontally
- `zt` to redraw, line `[count]` at top of window
- `zb` to redraw, line `[count]` at bottom of window
