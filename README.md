# Git-and-GitHub

### Basic Git Commands
***

| Command	          |    Explanation                               |
|:--------------      |:--------------------------------------------:|
| `git init      `    | Initialize a git repository                 |
| `git add .`         |       To stage files in the repository      | 
| `git commit -a `    | Stages files automatically                   |
| `git show`          | Show the differences in various commits      | 
| `git diff --staged` | Will show all staged files compared to the named commit |
| `git add -p   `     | Allows a user to review patches to add to the current commit |
| `git mv filename newname`| To rename a file                                        |
| `git rm   `         | Similar to the Linux `rm` command, this deletes, or removes a file 

### Review Changes

|       Command	                |    Explanation                   |
|:----------------------        |:--------------------------------:|
|  `git commit -a `                |	Stages files automatically
|  `git log -p  `        |  Produces patch text
|  `git show `      | 	Shows various objects
|  `git diff `     |   	show the differences in various commits
|  `git diff --staged`     |   show all staged files compared to the named commit
|  `git add -p ` | 	Review patches to add to the current commit

### Revert Changes
***

|       Command	                |    Explanation                   
|:----------------------        |:--------------------------------:|
|  `$ git checkout file1 `                |	Restores files to the latest stored snapshot
|  `git reset HEAD <file>`        | Unstage the file to current commit (HEAD)
| `git revert commit-id`        | Undo changes but retains history
|  ` git stash ` | 	Discard all local changes, but save them for later:
| `git stash pop` | Redo previously stashed changes and removes them from stashed list
|  `git reset --hard` |   	Discard everything permanently
|  `git reset --flag <commitid>` | Delete and undo changes after the commitid

### Git Branches and Merging Cheat Sheet
***

|       Command	                |    Explanation                   |
|:----------------------        |:--------------------------------:|
|  `git branch `                |	Used to manage    branches
|  `git branch <name>  `        |  Creates the branch
|  `git branch -d <name> `      | Deletes the branch
|  `git branch -D <name>  `     |   	Forcibly deletes the branch
|  `git checkout <branch>`     |  Switches to a branch.
|  `git checkout -b <branch>  ` | 	Creates a new branch and switches to it.
|  `git merge <branch>`         | Merge joins branches together.
|  `git merge --abort`          | To abort merge If there are merge conflicts
|  `git log --graph --oneline`  | Summarized view of the commit history for a repo.



# File System Commands
***

`ls`- used to list files and directories
`mkdir` - used to create a new directory
`cd` - used to change directories
`rm` - used to remove files and directories

# Git Config 
----
### `$ git --version`

### `git help --all`

### sets up Git with your name
`$ git config --global user.name "<Your-Full-Name>"`

### sets up Git with your email
`$ git config --global user.email "<your-email-address>"`

### makes sure that Git output is colored
`$ git config --global color.ui auto`

### displays the original state in a conflict
`$ git config --global merge.conflictstyle diff3`

### `$ git config --list`
Shows all configurations.

### Initiate Git Repository
`$ git init`

### Clone Project And Use Different project name
$ git clone https://github.com/udacity/course-git-blog-project NewName

### `$ git ls-files`
Shows files in the current repository.
`$ git ls-files --others --exclude-standard` shows all files including untracked files.

# Review Repo's History
___
### `$ git log`
Navigating The Log
If you're not used to a pager on the command line, navigating in Less can be a bit odd. Here are some helpful keys:

- to scroll down, press
j or ? to move down one line at a time
d to move by half the page screen
f to move by a whole page screen
- to scroll up, press
k or ? to move _up_ one line at a time
u to move by half the page screen
b to move by a whole page screen
- press q to quit out of the log (returns to the regular command prompt)

### `$ git log --oneline`
Short sha and commit message

### `$ git log --stat`
The git log command has a flag that can be used to display the files that have been changed in the commit, as well as the number of lines that have been added or deleted. The flag is --stat ("stat" is short for "statistics")

### `$ git log -p`
The git log command has a flag that can be used to display the actual changes made to a file. The flag is --patch which can be shortened to just -p:
 - the lines where the file is added and how many lines there are
-15,83 indicates that the old version (represented by the -) started at line 15 and that the file had 83 lines
+15,85 indicates that the current version (represented by the +) starts at line 15 and that there are now 85 lines...these 85 lines are shown in the patch below

### `$ git show [SHA]`
The other command that shows a specific commit is git show:
Running it like the example above will only display the most recent commit. Typically, a SHA is provided as a final argument:
`$ git show fdf5493`

### `$ git log --pretty=format:"%h - %cn, %cr : %s"`


### Table 2. Common options to git log (Ref: Git Book)
Option	Description
* `-p`
  * Show the patch introduced with each commit.
* `--stat`
    * Show statistics for files modified in each commit.
* `--name-status`
    * Show the list of files affected with added/modified/deleted information as well.
* `--relative-date`
    * Display the date in a relative format (for example, “2 weeks ago”) instead of using the full date format.
* `--graph`
    *  Display an ASCII graph of the branch and merge history beside the log output.
* `--pretty`
    * Show commits in an alternate format. Options include oneline, short, full, fuller, and format (where you specify your own format).
* `--oneline`
    * Shorthand for --pretty=oneline --abbrev-commit used together.

### `$ git log --since=2.weeks`

### `$ git status -sb`
Show git status in smaller format. Also includes the branch it is on

# Add Commits to a Repo 

### `$ git add <file1> <file2> … <fileN>`
The git add command is used to move files from the Working Directory to the Staging Index.

### `$ git commit -m "Initial commit"`
to commit the changes to one file `$ git commit file1`
 to commit all changes,, any of these forms will do it: 
```$ git commit
$ git commit ./
$ git commit -a  
```
`$ git commit -a -m "Message"` commit all changes skipping the staging area. useful for small commits. But it doesn't add or commit untracked files.

### `$ git diff`
The git diff command will show you the changes that have not yet been staged.
`$ git diff --staged` will show changes that have been staged but not yet committed.

### .gitignore
blank lines can be used for spacing
\# - marks line as a comment
\* - matches 0 or more characters\
\? - matches 1 character
[abc] - matches a, b, _or_ c
\*\* - matches nested directories - 
`a/**/z` matches
a/z
a/b/z
a/b/c/z

# Tagging & Branching 
***
### `$ git tag -a beta -m "message"`
To add a tag
To add a tag to specefic commit: `$ git tag ver_10 08d869aa8683703c4a60fdc574dd0809f9b073cd` 
or `$ git tag ver_10 08d869`
The numbered string is commit hash
To revert to the development point labeled by ver_10 would be: `$ git checkout ver_10`
### `$ git tag -d tagName`
To delete a tag

### `$ git branch ` 
Shows the current branch

### `$ git branch sidebar`
Create a new branch named sidebar

### `$ git branch checkout sidebar`
Switches the current working directory to sidebar branch 

### `$ git branch -d sidebar`
To force deletion, you need to use a capital D flag - git branch -D sidebar.

### `$ git checkout -b footer master`
Let's use this new feature of the git checkout command to create our new footer branch and have this footer branch start at the same location as the master branch.

### `$ git log --oneline --graph --all`
Wouldn't it be nice if we could see all branches at once in the git log output.

### `$ git merge <name-of-branch-to-merge-in>`
When we merge, we're merging some other branch into the current (checked-out) branch.

There are two types of merges:

- Fast-forward merge 
	- The branch being merged in must be ahead of the checked out branch. 
	- The checked out branch's pointer will just be moved forward to point to the same commit as the other branch.
- The regular type of merge  (Merge complict may arise here)
  - Two divergent branches are combined
  - a merge commit is created

##### Commit Merge Conflict
- locate and remove all lines with merge conflict indicators
- determine what to keep
- save the file(s)
- stage the file(s)
- make a commit
### `$ git merge --abort`
Aborting merge if merge conflicts arise. Pull back to latest commit.

# Undoing Changes
___
### `$ git checkout file1`
Git checkout restores files to the latest stored snapshot, reverting any changes before staging.

### `$ git reset HEAD filename`
Useful if you satage a change you don't want to commit.
Unstaged changes before commit. Changes are still in working directory.

### ` $ git reset --hard HEAD^`
If you make a merge on the wrong branch, use this command to undo the merge

### `$ git commit --amend -m "an updated commit message"`
Update the last commit with updated commit message. 
If you just want to update the code with same commit message: `$ git commit --amend --no-edit`
 > Avoid amending a commit that other developers have based their work on.

### `$ git revert <SHA-of-commit-to-revert>`

This command:
* will undo the changes that were made by the provided commit
* creates a new commit to record the change

### Git Reset
> Resetting is dangerous. Before reset do - `$ git branch backup`

Git reset can do: 
- move the HEAD and current branch pointer to the referenced commit
- erase commits with the --hard flag
- moves committed changes to the staging index with the --soft flag
- unstages committed changes --mixed flag

Ancestry References
`^` – indicates the parent commit
`~` – indicates the first parent commit

The flags are:
- `--soft`: just moves the current branch to prior commit object (index unchanged in this case)
- `--mixed`:(default): also updates the index to match new head (un-stages everything)
- `--hard`: same as --mixed, but also updates working directory to match new head (un-edits your files).

`$ git reset --hard HEAD^`

### Tidying Repositories
As your project grows through a series of commits, your repository may grow large in size. You can optimize and compact your repository by issuing git gc, as in:
`$ git gc` where gc = garbage collection

Checking for error:`$ git fsck` 
Fix error: `$ git prune` 

### `$ git blame file2`
Shows who made which changes


