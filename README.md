# scripts
Helpful scrips for git and other things

## Git scripts

A collection of scripts for frequent git tasks on the command line. These scripts must be run in a directory under git source control.

### gadd: git add

The `gadd` script will output a numbered list of files with unstaged changes in the current repo, and a prompt for the user to enter a number.

```
> gadd
Modified files:
     1  example/File1
     2  example/File2
     3  someOtherFile1
     4  someOtherFile2
Select file to add:
```

Enter the number for the file you want to stage and the script will run `git add --patch` for that file, allowing changes to be selectively staged.

### gres: git restore

Like `gadd` but runs `git restore --patch` for the selected file. Allowing changes to be selectively restored.

### gdiff: git diff

The `gdiff` script will output a numbered list of files with unstaged changes in the current repo, and a prompt for the user to enter a number.

```
> gdiff
Modified files:
     1  example/File1
     2  example/File2
     3  someOtherFile1
     4  someOtherFile2
Select file to diff:
```

Selecting a file will show the diff for that file.

### gdiffc: git diff (for commits)

The `gdiffc` script will output a numbered list of commits, for all commits upto, but not including, the most recent merge commit in the history. Commits are listed in order starting with the most recent.

```
> gdiffc
     1  c25a503dd4 Add support for X
     2  430f4f2d32 Make change to Y
     3  8e5550cda9 Move function X to file Z
Select a commit to diff:
```

Selecting a commit will show the diff between that commit and its parent, i.e., the diff of all changes made by the selected commit.

### greb: git interactive rebase

The `greb` script will output a numbered list of commits, for all commits upto, but not including, the most recent merge commit in the history. Commits are listed in order starting with the most recent.

```
> greb
     1  c25a503dd4 Add support for X
     2  430f4f2d32 Make change to Y
     3  8e5550cda9 Move function X to file Z
Select a commit to start rebase:
```

Selecting a commit will run `git rebase -i <selected commit>^` starting an interactive rebase session for the selected commit and all more recent commits.


### `gck`: git checkout

The `gck` script will output a numbered list of local branches.

```
> gck
Local branches:
     1  * branchX  c25a503dd4 [origin/branchX] Some commit message for X
     2    branchY  68a62e4f04 Some commit message for Y
     3    branchZ  436206cd84 [origin/branchZ] Some commit message for Z
Select branch to checkout:
```

Selecting a branch will checkout that branch.


TODO: Document more of the scripts
