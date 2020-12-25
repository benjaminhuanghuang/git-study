- blob — contents of a file

In git, the contents of files are stored in objects called blobs, binary large objects.

Every blob in git is identified by its SHA-1 hash

- tree — a directory listing (of blobs and trees).

In git, the equivalent of a directory is a tree. A tree is basically a directory listing, referring to blobs as well as other trees.


- commit — a snapshot of the working tree.
In git, a snapshot is a commit. A commit object includes a pointer to the main tree (the root directory), as well as other meta-data such as the committer, a commit message and the commit time.

In most cases, a commit also has one or more parent commits — the previous snapshot(s). Of course, commit objects are also identified by their SHA-1 hashes. These are the hashes we are used to seeing when we use git log.

Every commit holds the entire snapshot, not just diffs from the previous commit(s).

- branch: a named reference to a commit.

branch points to the latest commit in the line of development we are currently working on.

command
```
 git branch test
```
creating a pointer that points to the same commit as the branch we are currently on.

git keeps a special pointer called **HEAD**. Usually, HEAD points to a branch, which in turns points to a commit. 

- repository (in short: repo) is a collection of commits
A repository also includes things other than our code files, such as HEAD, branches, and so on
