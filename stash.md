## Git stash

  This command takes you uncommited changes,saves them away for later use,and then revert them from your working copy

    git stash
    git stash pop             # reapply stashed changes, and drop the stash
    git stash list   
    git stash apply stash@{x} # re-apply stash changes, and keep the stash
    git stash drop  stash@{x} # drop stash changes


  it will not stash new file which has not yet been staged, and these files have been ignored.
  
  ^-u^ or( ^--include-untracked^) tells git stash to also stash your untracked files
  ^-a^ or( ^--all^) 

### Viewing stash diffs
    
    git stash show     # view summary of a stash
    git stash show -p  # view the full diff of stash

### Partial stashes

    git stash -p   # need to confirm which file need to stash

### Creating a branch from your stash

    git stash branch add-style statsh@{1}
