# md5l
Small shell utilities for generating and maintaining .md5 manifest files.

md5l creates or updates the manifest for one or more directories.

md5lr recursively traverses directory trees and invokes md5l for each directory.

The generated manifests are compatible with the output of md5sum (except the optional * marker is omitted).

## Features
* Generate .md5 manifests for one or more directories.
* Recursively process directory trees.
* Rewrite manifests only when their contents actually change.
* Keep backups of previous manifest versions.
* Record checksum errors in a separate log.
* Use only plain text files - no database or external services.
* Small shell scripts following the UNIX philosophy.

## Typical workflow

After modifying files, run `md5l` or `md5lr.`

If a manifest changes, the previous version is preserved as `.md5~`, allowing you to inspect what changed:

`find . -name ".m*~"`

Comparing the old and new manifests with `diff` or `vimdiff` shows exactly which files were added, removed, renamed, or modified. Since entries are sorted by checksum rather than filename, file renames are easy to recognize.

Removing unnecessary `.md5.*~` backups.

## Status

These utilities were developed for personal use and have been used in daily workflows for years. They are published because they may be useful to others who maintain collections of files together with checksum manifests.
