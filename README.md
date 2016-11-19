# Do Something With A Temporary Directory

A subprocess is often an ideal wrapper for a given task.

An often sought for wrapper is that of creating a temporary directory to make
room for some scratch-space to work with, and to purge the directory when the
task is done.

Although popular programming languages have mechanisms for doing this inside
the language (e.g., a
[try-catch-finally](https://en.wikipedia.org/w/index.php?title=Exception_handling_syntax&oldid=736583603),
or
[defer](https://web.archive.org/web/20160419202839/http://blog.golang.org/defer-panic-and-recover)
statement), there is ill support for this across language barriers. Besides,
most programming languages have a hard time offering a barrier like the one
offered by a good old subprocess.

[tmpdir](tmpdir) leverages the widely accessible process abstraction instead.

[tmpdir](tmpdir) aims to be cross-platform and easy to use: [tmpdir](tmpdir) is
a small, self-contained Python executable. This makes it easy to just copy
[tmpdir](tmpdir) into your source tree and use it.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/oleks/tmpdir/blob/master/tmpdir)

## Exploratory Examples

The following examples assume that you've added the path to [tmpdir](tmpdir) to
your `PATH` environment variable.

Prefixing your command with `tmpdir` will change working directory to the
created temporary directory and execute the command in there:

```
~$ tmpdir bash
/tmp/tmpPOFIGL$ 
```

You can also copy a file or directory (e.g., student submission) into the temporary
directory with the `-c|--copy` argument:

```
~$ tmpdir --copy /etc/passwd bash
/tmp/tmpLVfhmy$ ls
passwd
/tmp/tmpLVfhmy$ diff -u passwd /etc/passwd
/tmp/tmpLVfhmy$
```
