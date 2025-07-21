# <center><img src="https://git-scm.com/images/logos/downloads/Git-Logo-1788C.png" height="70"></center>

**Git** is a free and open-source distributed version control system, created by [**Linus Torvalds**](https://github.com/torvalds), the creator of Linux. It is used to track changes in source code during software development. It allows developers to collaborate on projects, track changes, and revert to previous versions, making it an essential tool for modern software development. Think of it as a time machine for your code.

---

# Version Control System

A Version Control System is a tool that records changes to files over time, allowing you to recall specific versions, collaborate with others, and recover data when needed.
**Examples:** Git, BitBucket, Subversion, Mercurial, etc.

## What a VCS Does:

1. **Track Changes Over Time**
    - Every modification to files is recorded, so you can go back and see what changed, when, and by whom.
2. **Revert to Earlier Versions**
    - You can roll back specific files or even the whole project to a previous working state if something breaks.
3. **Compare Changes**
    - You can easily view differences between versions to understand what was changed.
4. **Identify Who Changed What**
    - Useful in team environments for accountability and debugging ("Who introduced this bug?").
5. **Recover From Mistakes**
    - Even if you accidentally delete or corrupt a file, you can recover it from version history.

## Types Of VCS

Earlier, people's version-control method of choice is to copy file into another directory (perhaps a time-stamped directory, if they're clever). This approach was very common because it is so simple, but it is also incredibly error prone. It is easy to forget which directory you're in and accidentally write to the wrong file or copy over files you don't mean to.

### Local Version Control System

To deal with this issue, programmers long ago developed Local VCS that had a simple database that kept all the changes to files under revision control. It stores this info on the local machine.
**Example:** RCS
<center><img src="https://git-scm.com/book/en/v2/images/local.png" height="300"></center>

### Centralized Version Control System

Programmers then developed other type of VCS, that allows them to collaborate with others.
This Centralized Version Control Systems (CVCSs) have a single server that contains all the versioned files.
**Example:** Subversion (SVN), CVS, Perforce

<center><img src="https://git-scm.com/book/en/v2/images/centralized.png" width="500"></center>


### Distributed Version Control System

CVCSs allows collaboration, but, whenever you have the entire history of the project in a single place, you risk losing everything.
So, Distributed Version Control Systems (DVCSs) were developed, in which, every client have a full copy of the project on their local system.
**Example:** Git, Mercurial or Darcs

<center><img src="https://git-scm.com/book/en/v2/images/distributed.png" height="500"></center>

---

# History of Git

The Linux kernel is an open-source software project of considerable scale. In its early years, changes to the kernel were shared as patches and archived files, typically distributed via email. This manual process made collaboration challenging as the project grew.

In 2002, the Linux kernel project adopted BitKeeper, a proprietary distributed version control system (DVCS). BitKeeper was provided free of charge to the Linux development community, but with specific licensing conditions.

This arrangement continued until 2005, when a member of the Linux development community violated one of BitKeeper's license terms. As a result, the free license was revoked, leaving the Linux community without a version control system that met their needs.

In response, Linus Torvalds started building a new version control system. He needed a new version control system that could handle the unique challenges of Linux kernel development, including:

- Speed
- Simple design
- Strong support for non-linear development
- Fully distributed
- Strong guarantees of data integrity
- Able to handle large projects like the Linux kernel efficiently (speed and data size)

And the amazing part? Linus Torvalds developed a usable version of Git in just about 10 days. Within that short span, Git had already become capable enough to self-host — meaning it was being used to manage its own source code.

Linus stopped being the maintainer of Git a few months later, handing it off to [Junio Hamano](https://github.com/gitster), who continues to maintain it today.

---

# What is Git?

<center><img src="https://imgs.xkcd.com/comics/git.png"></center>

Git is a distributed version control system, primarily used from the command line. While it's tempting to just memorize a list of commands, that approach only gets you so far. To truly harness the power of Git, you need to understand how it sees and stores your data under the hood. So now, we'll begin by exploring the internal workings of Git, revealing the elegant design that makes it such a powerful tool.

Git is just a Directed Acyclic Graph (DAG) of objects, with a handful of different types of objects. They are all stored compressed and identified by an SHA-1 hash.

<center><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fe/Tred-G.svg/375px-Tred-G.svg.png" height="300"></center>

---

## Snapshots, Not Differences

The major difference between Git and any other VCS is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. These other systems think of the information they store as a set of files and the changes made to each file over time.

Git doesn't think of or store its data this way. Instead, Git thinks of its data more like a series of snapshots of a miniature filesystem. With Git, every time you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if files have not changed, Git doesn't store the file again, just a link to the previous identical file it has already stored. Git thinks about its data more like a stream of snapshots.

---

# Types of Objects in Git

## Blob

A blob (short for "binary large object") is the simplest type of object in Git. It represents the contents of a file, just a raw sequence of bytes. A blob stores the file's data, but not any metadata such as the filename, file permissions, or directory structure.
When a file is changed, a new blob will store complete file with all new changes.

<center><img src="https://shafiul.github.io/gitbook/assets/images/figure/object-blob.png"></center>

## Tree

Just like a folder contains files and other folders, a tree object in Git represents directories that can contain both blobs (file contents) and other tree objects (subdirectories). A tree object stores metadata such as filenames, file permissions, and references to the corresponding blobs or trees.
There is always a tree on root, pointing to the tree which contains stuff.

<center><img src="https://shafiul.github.io/gitbook/assets/images/figure/object-tree.png"></center>

## Commit

A commit refers to a tree that represents the state of the files at the time of the commit.
Each commit also contains the references to all its parent commits. If there are no parents of a commit, then it means it is an initial commit. If there are more than one parent then it is a merge.
The body of the commit is the commit message.
Commits are immutable in Git.

<center><img src="https://shafiul.github.io/gitbook/assets/images/figure/object-commit.png"></center>

---

<center><img src="https://shafiul.github.io/gitbook/assets/images/figure/objects-example.png"></center>

---

# Git References

Now, all objects can be identified by their SHA-1 hashes. But it's a bit inconvenient to remember strings of 40 hexadecimal characters. Git solves this problem by allowing us to store human-readable names for SHA-1 hashes, called "references". References are pointers to commits.
Unlike objects, which are immutable, references are mutable.

## The HEAD

It is a special reference which tells us, "where we currently are" in the history. It usually contains reference to some other reference and not to a commit itself. But sometimes, when it contains hash of a commit, then it is in "detached HEAD" state.

## Tags

Tags in Git are used to mark specific points in your commit history. They act like bookmarks or labels for commits, making it easy to reference them later. A tag is a type of reference that does not move, it always points to the same commit.

1. **Lightweight Tag**
    It is a simple pointer to a commit, that doesn't move. It just contains the hash of the commit it is pointing to.
2. **Annotated Tag**
    It is a full Git object stored in the repository.

---

# Repository

Now, we can define what (roughly) is a Git repository: It is the data objects and references.

On disk, all Git stores are objects and references: that's all there is to Git's data model. All git commands map to some manipulation of the commit DAG by adding objects and adding/updating references.

---

# The Working Directory

This the directory in which you are working. When you check-out a commit, your whole directory with all files is changed/replaced to match that commit (except ignored files).

---

# The Staging Area/Index

Unlike other, similar tools, Git does not commit changes directly from the working tree into the repository. Instead, changes are first registered in something called the index. Think of it as a way of “confirming” your changes, one by one, before doing a commit (which records all your approved changes at once). Some find it helpful to call it instead as the “staging area”, instead of the index.

---

# Commands

![](https://git-scm.com/book/en/v2/images/lifecycle.png)

There are various ways to do a single thing in git.

- [x] Some git-bash commands
    ```bash
    cd - Change directory
    pwd - Print working directory
    clear - Clears the terminal screen
    mkdir - Make directory = Create new directory
    rm - Remove = Removes a file or folder
    rmdir - Remove Directory = Removes a given directory
    mv - Move = Moves a given source to destination
    touch - Creates a new file
    ls - List directory
    cat - Displays the contents of a file
    less - Displays the contents of a file in multiple pages
    cp - Copies a file or folder to the given destination
    ls --help - Displays help of ls command
    ```

- [x] Initializing a Git repository 
    ```bash
    git init
    ```

- [x] Getting Help
    ```bash
    git command -h
    git command --help
    git help <command>
    ```

- [x] A look inside `.git`

- [x] Viewing the internals
    ```bash
    git cat-file -p <hash>
    ```

- [x] Working Tree and Staging area
    ```bash
    # Shows the working tree status
    git status

    # Short status of working tree
    # left: staging area
    # right: working tree
    git status --short
    git status -s
    ```
    
- [x] Tracked vs Untracked Changes 
    ```bash
    git add
    ```

- [x] Dual Nature of a Single File

- [x] Create History: Commit changes
    ```bash
    # Used to create a commit
    # it will open your default editor for commit message
    git commit

    # You can directly add commit msg without opening editor
    # using this command
    git commit -m "YOUR MESSAGE"

    # Commits all changes inside the working tree
    # except the untracked ones
    # without the need of adding changes to the working tree
    git commit -a

    # Shows extra information in the comments of commit message
    # that opens in the default editor
    git commit -v
    ```

- [x] Viewing logs
    ```bash
    # Show commit logs
    # List commits that are reachable by the current commit by following
    # the parent links
    git log
    
    # Draws an ASCII based representation of commit history
    git log --graph
    
    # Lists commit history in short
    git log --oneline

    ```
    - Limiting Log Output
        ```bash
        # Show last n commits
        git log -n <number>
        git log -<number>
        
        # Lists all the commits that are reachable by the given commit
        # You can give mulltiple commits
        # You can also put ^ in front of a commit to subtract its output
        git log <hash/ref>
    
        # The following syntax is short-hand for "^<commit1> <commit2>"
        git log <commit1>..<commit2>
        
        # Pretends all the refs along with HEAD are given as argument
        git log --all

        # Look for differences that change the number
        # of occurrences of the specified string in a file
        git log -S "name"

        # Lists all the commits that includes changes
        # in the specified <path>
        git log -- <path>
        ```

- [x] Ignoring
    There are some files you don't want git to add automatically or even show as untracked. Such as temp files, environment files, build artifacts, .etc.
    In such cases, you can create a file name `.gitignore` which lists all the files or directories to be ignored.
    You can also specify patterns to match multiple files of directories.

    **Rules for patterns:**
    - Blank lines and list starting with `#` are ignored.
    - Standard wildcard/glob patterns (`*`, `?`) are supported.
    - You can start patterns with `/` to avoid recursivity.
    - You can end patterns with `/` to specify directory otherwise it matches both files and directories.
    - You can negate a pattern by starting it with an `!`.
    - `[abc]`: Matches any character inside the brackets.
    - `[0-9]`: Matches one of the characters in the range (in this case 0 through 9.
    - Similarly, `[a-z]` matches any small case letter from a to z.
    - Two consecutive asterisks `**` between two slashes (`/`) matches zero or more directories.
    
    GitHub maintains a list of `.gitignore` files for different projects and languages at https://github.com/github/gitignore.
    
    You can have multiple `.gitignore` file inside different subdirectories. The rules from these nested `.gitignore` files apply only to the files under the directory where they are located.
    Linux Kernel source repository has 206 `.gitignore` files.

- [x] Viewing Differences
    ```bash
    # Compares working directory to staging area
    git diff
    
    # Compares staging area to last commit
    git diff --staged
    git diff --cached
    
    # Compare working directory to specific commit
    git diff <commit>
    
    # Compare working directory to last commit
    git diff HEAD

    # List all commits along with what changed in that commit
    git log -p or git log --patch

    # Differences in short
    git log --stat
    ```
    
- [x] Removing Files
    ```bash
    rm <file>
    git rm <file> or git add <file>
    ``` 
    
    ```bash
    git rm <file>
    ```
- [x] Moving Files
    ```bash
    mv <file> <dest>
    git rm <file>
    git add <dest>
    ```

    ```bash
    git mv <file> <dest>
    ```

- [x] Undo changes
    - [x] Amending previous commit
        ```bash
        git commit --amend
        ```
        Useful for adding some changed that you forgot to commit, and preventing cluttering your repo history with unnecessary commits
        
    - [x] Unstaging a staged file
        ```bash
        git reset HEAD <file> # old
        git restore --staged <file> # new
        ```
      
    - [x] Unmodifying a modified file
        ```bash
        git checkout -- <file> # old
        git restore <file> # new
        ```

- [x] Tagging
    ```bash
    git tag
    git tag --list
    git tag -l
    git tag -l "v0.1.*"
    git show <tag>
    ```
    - [x] Annotated Tags
        ```bash
        git tag -a "tagname" -m "message"
        git tag -a "tagname" <hash>
        ```
    - [x] Lightweight Tags
        ```bash
        git tag "tagname"
        ```
    - [x] Deleting tag
        ```bash
        git tag -d <tag>
        ```
- [ ] Branches
    Git's branching model is referred to as it's "killer feature".
    Git branches are lightweight, making branching operations nearly instantaneous, and switching back and forth between branches generally just as fast.
    Git encourages workflows that branch and merge often, even multiple times in a day.
    Creating a new branch in Git is as fast as creating a new file and writing 41 bytes to it.

    - [x] Listing Branches
        ```bash
        git branch
        git branch -v
        git branch --all
        git branch --merged
        git branch --no-merged
        ```
    - [x] Creating New Branches
        ```bash
        git branch <branchname>

        git checkout -b <branchname> # old
        git switch -c <branchname> # new
        ```
    - [x] Activating a branch
        ```bash
        git checkout <branchname> # old
        git switch branch # new
        ```
    - [x] Deleting a branch
        ```bash
        git branch -d <branchname>
        ```
    - [x] Changing a Branch Name
         ```bash
         git branch --move <oldname> <newname>
         ```
- Merging
    - [x] Basic Merge
        ```bash
          git merge <branchname>
        ```
    - [x] Fast-forwarding
    - [x] Three-Way Merge
    - [x] Merge Conflict


- [x] Reason behind the change of `master` to `main`

---

- [x] Bare repositories
    A Bare repository is a Git repository without a working directory, it only contains the contents of the .git directory.
    
    ```bash
    git init --bare <folder name>
    ```
    
- [ ] Git clone
    ```bash
    git clone <url> <folder_name>
    ```
    
- [x] Remotes
    Remote repositories are versions of your project that are hosted on the Internet or network somewhere.
    ```bash
    # list all remotes
    git remote
    git remote -v
    git remote -vv

    git remote add <name> <url>

    ```
- [x] Remote Tracking Branch
- [x] Setting upstream
    ```bash
    git branch --set-upstream-to=<remote>/<remote branch>
    ```

```bash
# Push local changes to remote
git push <remote> <local_branch>:<remote_branch>

# Fetch local changes to remote
git fetch <remote>
```
    


# References

- [How to explain git in simple words?](https://xosh.org/explain-git-in-simple-words/)
- [Git for Computer Scientists](https://eagain.net/articles/git-for-computer-scientists/)
- [Git from the Bottom Up](https://jwiegley.github.io/git-from-the-bottom-up/)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [The Git Community Book](https://shafiul.github.io/gitbook/index.html)
- [Learn Git Branching](https://learngitbranching.js.org/)
- [Oh Shit, Git!?!](https://ohshitgit.com)
- [Gitflow: Original](https://nvie.com/posts/a-successful-git-branching-model/)
- [Gitflow: Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Oneflow](https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow)
- [GitHub Flow](https://docs.github.com/en/get-started/using-github/github-flow)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)