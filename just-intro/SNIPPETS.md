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

