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

just

just --list

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

just --list

cd src
just ls
just top-ls

git add .
git cim '📃 directory part of demo'
```

## Make-like dependencies

```bash
```

## Documenting recipes

```bash
```

```bash
```

## Extracting data from TOML or JSON

```bash
```

## Creating a pull request

```bash
```

## Inline Perl or LUA

```bash
```

## github action

https://github.com/chicks-net/google-plus-posts-dumper/blob/main/.github/workflows/verify.yaml

```bash
mkdir -p .github/workflows
curl https://raw.githubusercontent.com/chicks-net/google-plus-posts-dumper/refs/heads/main/.github/workflows/verify.yaml -o .github/workflows/verify.yaml
view .github/workflows/verify.yaml

# ...
```

