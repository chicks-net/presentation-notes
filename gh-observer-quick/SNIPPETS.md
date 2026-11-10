# gh-observer quick snippets

The demo runs against a scratch repo - `chicks-net/gh-observer-demo` - built
in the prep section below, so the recording never waits on real work.  These
notes are committed as their own separate PR before recording, which lets
the slides render from the raw githubusercontent URLs the way `just-intro`
does.

## Pre-demo prep (before hitting record)

- [ ] This notes PR is merged to main so the slide URLs below work.
- [ ] Cap test recording verified - see the [Recordings](./README.md#recordings) checklist.
- [ ] Terminal at 109 col x 37 rows, font bumped for video scale.
- [ ] Do Not Disturb ON.
- [ ] `gh auth status` is happy.
- [ ] The external URLs still resolve - the dnscontrol PR and the gh-observer Actions run get swapped for fresher ones if GitHub has purged them.

The snippets use my git aliases (`co`, `cim`, `pushup`) from my global
gitconfig - https://github.com/chicks-net/chicks-home/blob/master/.gitconfig#L10

### Create the demo repo

```bash
gh repo create chicks-net/gh-observer-demo --public --description "demo repo for the gh-observer quick intro video" --add-readme --disable-issues --clone
cd gh-observer-demo
```

### Add workflows

A fast `lint` job (breakable on purpose) and a slow `test` job (live timers):

```bash
cat > .markdownlint.yml <<'YAML'
---
default: True
MD013: False
YAML
mkdir -p .github/workflows
cat > .github/workflows/ci.yml <<'YAML'
---
name: CI
on:
  push:
    branches:
      - main
  pull_request:
permissions:
  contents: read
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: DavidAnson/markdownlint-cli2-action@v19
  test:
    runs-on: ubuntu-latest
    steps:
      # no actions/checkout needed - this job only sleeps
      - run: sleep 45
      - run: echo "tests passed"
YAML
git add .github .markdownlint.yml && git cim '🪨 add CI workflows'
git push
```

### Warm up run history

Historical averages need a few completed runs, so push a few trivial
commits (each push is one completed run):

```bash
for i in 1 2 3; do date >> warmups.txt && git add warmups.txt && git cim "🕒 warm up run history $i" && git push || break; done
```

Leave the shell in the demo clone - all demo beats below run from there.

## Start

### Opening title

```bash
clear ; glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/gh-observer-quick/OPENING.md
```

### Why should we try this tool? (Intro)

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/gh-observer-quick/FEATURES.md
```

### Install the extension

```bash
gh extension install fini-net/gh-observer

# already installed (likely, this repo lists it as a prerequisite)?
gh extension upgrade observer
```

### Open the demo PR

```bash
cd gh-observer-demo   # or wherever the clone lives
git co -b demo-change
printf '\ndemo change for the gh-observer quick intro video\n' >> README.md
git add README.md && git cim '🪨 demo change'
git pushup
gh pr create --title "🪨 demo change" --body "Watch this PR's checks with gh-observer."
```

### The old way (the pain)

```bash
gh pr checks --watch
# no runtimes, no queue latency, no hint during the startup delay.
# make the point, then Ctrl+C before it eats the whole video.
```

### Watch the same PR with gh-observer

```bash
gh observer
```

- auto-detects the PR from the current branch
- "Waiting for Actions to start..." with elapsed seconds during GitHub's 30-90s queue delay
- queue latency when jobs appear, live run timers, historical averages per job
- `j`/`k` to scroll if output overflows; `q` to quit
- lint finishes fast; test runs 45s - let it complete so the summary lands, or `q` and move on

## Break markdownlint on purpose

The same MD032 error from the gh-observer README example, on purpose:

```bash
printf 'This list touches the text above so MD032 will complain:\n- no blank line before this list\n' > DEMO.md
git add DEMO.md && git cim '💥 break markdownlint on purpose'
git push
```

```bash
gh observer
```

- lint fails fast with the error lines inline - no browser needed

## Fix it and take a quick snapshot

```bash
rm DEMO.md
git add -A && git cim '✅ fix the markdownlint error'
git push
```

```bash
gh observer --quick
```

- `--quick` skips the historical averages fetch for an instant snapshot

## Repo dashboard

```bash
gh observer --repo chicks-net/gh-observer-demo
```

- every open PR with checks grouped under it, plus standalone branch runs
- completed checks fade out on their own
- `q` to quit - repo mode keeps running on purpose

## Watch a PR I have never cloned

```bash
gh observer https://github.com/StackExchange/dnscontrol/pull/3941
```

- full URL, no clone needed; a PR with finished checks shows its final summary

## Optional: watch an Actions run

```bash
gh observer https://github.com/fini-net/gh-observer/actions/runs/25856656092
```

- works the same for runs that are not tied to a PR

## Exit codes for scripts

```bash
gh observer https://github.com/StackExchange/dnscontrol/pull/3941 ; echo "exit code: $?"

# or wait on your own PR from a script
gh observer && echo "All checks passed!"
```

- 0 = everything passed, 1 = something failed

## Conclusion

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/gh-observer-quick/CONCLUSION.md
```

## Post-demo

- [ ] Merge the demo PR (or close it and reuse the repo for practice takes).
- [ ] Fill in the Cap trial notes in the [README](./README.md#recordings).
- [ ] Update the root README entry once the video is recorded.
