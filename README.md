# Sysadmin Scripts Collection

A collection of scripts that simplify maintainance of our servers:

## Styleguide

### Shell scripts

Primary target for these scripts is a system running FreeBSD. We adhere to Google [Style Guide](https://google.github.io/styleguide/shell.xml) with these exceptions:
  - We don't use `bash` for our scripts. Our goal is that those scripts will run on any POSIX compatible shell (notably `sh`), which `bash` is not.
  - Local variables therefore cannot use keyword `local`.
  - Indentation should be one tab `\t` (consistency with heredoc, compatibility with Makefile…).
  - Maximum line length should be 100 characters, but is not enforced.

It is also recommended to check those scripts with [shellcheck](http://www.shellcheck.net/).

### Python scripts

We fully adhere to [PEP-8](https://www.python.org/dev/peps/pep-0008/), except the maximum line length, which should be 100.

We prefer Python 3 where possible.
  
## Scripts

### `properly`

Runs an administrative/maintenance command properly: with backups before and after, logging the action and not leaving a mess behind.

### `sudo-git-wrapper`

Use git as root with your user config.

### `metadata-git-wrapper`

Simple minimalistic wrapper around git which stores metadata about files: for `/etc` under git (FreeBSD only).

### `repo-dirty-checker`

Periodically checks whether someone has left a mess behind in `/etc` under git.

### `zfs-snapmanage-shell`

Limited login shell which allows management of zfs snapshots only. Optionally it can limit operation only to datasets specific to a given jail.
