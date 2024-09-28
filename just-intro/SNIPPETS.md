# just intro snippets

## Start

### Opening title

```bash
glow https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/just-intro/OPENING.md
```

### Why should we try this tool?

```bash
glow https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/just-intro/FEATURES.md
```

### Create repo

```bash
gh repo create chicks-net/just-demo2 --public --description "just a demo of just" --add-readme --homepage "https://github.com/chicks-net/presentation-notes/tree/main/just-intro" --disable-issues --gitignore Rust --clone
```

```bash
cd just-demo2
```

### Rust hello world

```bash
cargo init .
cargo run
```

### Rust in just

```bash
echo 'try:
  cargo run --' > justfile
```

```bash
bat justfile

just

just --list
```

```bash
git help -a | tail -14
git add .
git cim '🪨 base of demo'
git push
```

## Changing directories or not

```bash
echo 'try:
  cargo run --

[no-cd]
ls:
  ls -ltr

top-ls:
  ls -ltr' > justfile
```

```bash
bat justfile
just --list
```

```bash
cd src
just ls
just top-ls
```

```bash
cd ..
git add .
git cim '📃 directory part of demo'
```

## Make-like dependencies

```bash
echo 'try: check
  cargo run --

check:
  cargo clippy
  cargo test --workspace

newdep crate_name: check
  cargo add {{crate_name}}
  cargo doc' > justfile
```

```bash
bat justfile
just --list
```

```bash
just check
just
just newdep glob
```

```bash
git stp
git diff Cargo.toml
git add .
git cim '🚜 dependencies and argument part of demo'
```

## Documenting recipes

```bash
echo '# run it again
try: check
  cargo run --

# unit testing
check:
  cargo clippy
  cargo test --workspace

# add a crate
newdep crate_name: check
  cargo add {{crate_name}}
  cargo doc' > justfile
```

```bash
git diff
just --list
```

```bash
git add .
git cim '📚 documentation is easy'
```

## Tabs or spaces are fine

Last overwrite to show how small the diff is.

```bash
echo '# run it again
try: check
  cargo run --

# unit testing
check:
    cargo clippy
    cargo test --workspace

# add a crate
newdep crate_name: check
    cargo add {{crate_name}}
    cargo doc' > justfile
```

```bash
git diff
just --list
just check
```

```bash
git add . &&  git cim '🚚 tabs or spaces are fine'
```
## Extracting data from TOML or JSON

```bash
echo '
# extract version
@version:
  toml get -r Cargo.toml package.version' >> justfile
```

```bash
git diff
just --list
just version
just --version
```

```bash
git add . &&  git cim '📖 write extraction formula once, reuse infinite times'
```

```bash
git push
```

## Creating a pull request

```bash
echo '
release_branch := "main"

# error if not on a git branch
on_a_branch:
  #!/bin/bash

  # thanks to https://stackoverflow.com/a/12142066/2002471

  if [[ $(git rev-parse --abbrev-ref HEAD) == "{{release_branch}}" ]]; then
    echo "You are on branch {{release_branch}} (the release branch) so you are not ready to start a PR."
    exit 100
  fi' >> justfile
```

```bash
bat justfile
just on_a_branch
git co -b example_branch
just on_a_branch
echo $?
```

```bash
echo '
# thanks to https://stackoverflow.com/a/7293026/2002471 for the perfect git incantation
last_commit_message := `git log -1 --pretty=%B | grep '.'`

# PR create
pr: on_a_branch
  git stp
  git pushup
  gh pr create --title "{{last_commit_message}}" --body "{{last_commit_message}} (Automated in 'justfile'.)"

# PR merge and return to main branch
merge: on_a_branch
  gh pr merge -s
  git co {{release_branch}}
  git pull' >> justfile
```

```bash
git diff
git add . &&  git cim '📓 creating a pull request without touching the browser'
```

```bash
git hist
just --list
just pr
just merge
```

## Inline Perl and LUA

```bash
git co -b all_scripting_languages_welcomed
```

```bash
echo '
# say hello chicks
hello_chicks:
        #!/usr/bin/env perl
        print "hello chicks\\n";

# say howdy internet people
howdy_net:
        #!/usr/bin/env lua
        print("howdy internet people");' >> justfile
```

```bash
git diff
just --list
just hello_chicks
just howdy_net
```

```bash
git add . &&  git cim '📗 add fun scripting language examples'
```

```bash
just br
just pr
just merge
```

## github action

```bash
git co -b add-some-github-action
```

```bash
mkdir -p .github/workflows
```

```bash
curl https://raw.githubusercontent.com/chicks-net/google-plus-posts-dumper/refs/heads/main/.github/workflows/verify.yaml -o .github/workflows/verify.yaml
```

```bash
bat .github/workflows/verify.yaml
```

```bash
git add .github
git stp
git cim '📒 add github action'
just pr
# gh pr view --web
gh workflow view Verify
gh workflow view Verify
gh workflow view Verify
just merge
```

### Why should we try this tool?

```bash
glow https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/just-intro/CONCLUSION.md
```
