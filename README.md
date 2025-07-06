# gh-gpg-import

A `gh` extension to import GPG keys from GitHub users' signing keys.

## Quickstart

1. `gh extension install WillyJL/gh-gpg-import`
1. `gh gpg-import <organization>/<team>`
1. Profit! :moneybag: :money_with_wings: :money_mouth_face: :money_with_wings: :moneybag:

## Usage

`gh-gpg-import` extension will import all public signing keys for users individually or all users within a GitHub team.

```shell
$ gh gpg-import --help

Import GPG keys from GitHub users.

USAGE
  gh-gpg-import [options] <organization>/<team>
  gh-gpg-import [options] <user>

FLAGS
  -d, --debug                         Enable debugging
```

The resulting GPG public signing keys for each user will be imported into the local GPG database of known keys.  For commits created on `github.com` web UI you will need GitHub's own keys with `gh gpg-import GitHub`:

```
Importing GPG keys for GitHub web commits
gpg: key 4AEE18F83AFDEB23: "GitHub (web-flow commit signing) <noreply@github.com>" imported
gpg: key B5690EEEBB952194: "GitHub <noreply@github.com>" imported
gpg: Total number processed: 2
gpg:               imported: 2
```

## Setup

Like any other `gh` CLI extension, `gh-gpg-import` is trivial to install or upgrade and works on most operating systems:

- **Installation**

  ```shell
  gh extension install WillyJL/gh-gpg-import
  ```
  
  _For more information: [`gh extension install`](https://cli.github.com/manual/gh_extension_install)_

- **Upgrade**

  ```shell
  gh extension upgrade gpg-import
  ```

  _For more information: [`gh extension upgrade`](https://cli.github.com/manual/gh_extension_upgrade)_

## Acknowledgements

This extension is heavily based on [gh-ssh-allowed-signers](https://github.com/andyfeller/gh-ssh-allowed-signers).
Since this extension aimed to fulfill a very similar purpose, just with a different kind of keys stored in a different manner, I opted to fork and change just what was necessary.
