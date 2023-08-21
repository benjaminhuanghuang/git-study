The `git init` command creates a new empty repository.

Git stores all repository data locally, in a subdirectory called ".git"

You should see the following directories in .git directory:
```
    info/
    objects/
    hooks/
    logs/
    refs/
```

The directory you’re interested in is the objects directory. In Git, the most common objects are:
- Commits: Structures that hold metadata about your commit, as well as the pointers to the parent commit and the files underneath.
- Trees: Tree structures of all the files contained in a commit.
- Blobs: Compressed collections of files in the tree.
```
    objects
    ├── 02
    │   ├── 1f10a861cb8a8b904aac751226c67e42fadbf5
    │   └── 8f2d5e0a0f99902638039794149dfa0126bede
    ├── 05
    │   └── 66b505b18787bbc710aeef2c8981b0e13810f9
```

When Git stores objects, instead of dumping them all into a single directory, git structures them neatly into a tree. 
Git takes the first two characters of your object’s hash, uses that as the directory name, and then uses the remaining 38 characters as the object identifier.




So we can store an object, but how would we refer to it later? We're going to use the hash as the id of object .

A hash function can take a blob of arbitrary length and produce a small "fingerprint" with a fixed length.
Hash functions such as SHA-1 guarantee that different blobs have different fingerprints 

```
$ echo -n this is cool | sha1sum
60f51187e76a9de0ff3df31f051bde04da2da891

$ echo -n this is cooler | sha1sum
f3c953b792f9ab39d1be0bdab7ab5f8350593004
```

## Workflow of saving a file to git repository:
- Get the path of the file to store.
- Read the file.
- Hash the content of the file using SHA-1.
- Store the file under ".git/objects/{the SHA-1 hash}".

When real Git stores objects it does a few extra things, such as writing the size of the object to the file as well, 
compressing them and dividing the objects into 256 directories. 
This is done to avoid having directories with huge number of files, which can hurt performance. 

## Workflow of retrieve a file to git repository:

Git provides a way to look at the contents of a compressed Git object: `git cat-file`. 
```
    # -p option here tells Git to figure out what type of object it’s dealing with and to provide appropriately formatted output.
    git cat-file -p d83ab2b
```
This decompresses the object and writes it out to your console in a human-readable form.

```
def get_object (oid):
    with open (f'{GIT_DIR}/objects/{oid}', 'rb') as f:
        return f.read ()
```
