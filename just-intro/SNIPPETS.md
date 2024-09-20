# just intro snippets

## Start

### Create repo

```bash
gh repo create chicks-net/just-demo-pre1 --private --description "demo of just" --readme
gh repo clone chicks-net/just-demo-pre1
cd just-demo-pre1
```

### Rust hello world

```bash
cargo init .
cargo run --
```

### Rust in just

```bash
echo 'try:
  cargo run --' > justfile
cat justfile
```

```bash
just

just --list
```

```bash
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
cat justfile
```

```bash
just --list
```

```bash
cd src
just ls
just top-ls
```

```bash
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
git diff
cat justfile
```

```bash
just check
just
just newdep glob
```

```bash
git stp
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
git add .
git cim '📖 write extraction formula once, reuse infinite times'
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
git diff
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
git add .
git cim '📓 creating a pull request without touching the browser'
```

```bash
git hist
just --list
just pr
just merge
```

## Inline Perl or LUA

```bash
```

## github action

```bash
mkdir -p .github/workflows
curl https://raw.githubusercontent.com/chicks-net/google-plus-posts-dumper/refs/heads/main/.github/workflows/verify.yaml -o .github/workflows/verify.yaml
view .github/workflows/verify.yaml

# ...
```

