# just intro snippets

## Setup

iTerm2 with

- Pastel dark background
- 111 columns and 40 rows
- tmux messed up the colors (ugh!) so I couldn't have the clock in the terminal at the same time (sigh)

## Start

### Opening title

```bash
clear ; glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/OPENING.md
```

### Why should we try this tool? (Intro)

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/FEATURES.md
```

### Agenda

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/AGENDA.md
```

### What is dnscontrol?

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/FEATURES_dnscontrol.md
```

### What is coredns?

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/FEATURES_coredns.md
```

### What is just?

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/FEATURES_just.md
```

## dnscontrol in action

### Test in a clean environment (optional)

```bash
podman run -it -e GITHUB_TOKEN=$(gh auth token) -e DEBIAN_FRONTEND=noninteractive -e TZ=UTC ubuntu:24.04 bash -c "apt update && apt install -y git gh podman rustup gcc jq golang dnsutils && go install github.com/StackExchange/dnscontrol/v4@latest && rustup default stable && cargo install just && bash"
```

```bash
PATH=$PATH:/root/.cargo/bin:/root/go/bin && cd root
```

### Clone repo

```bash
gh repo clone fini-net/fini-coredns-example
```

```bash
cd fini-coredns-example
```

### View code for defining domains

### List just recipes

```bash
just
```

Just a preview - we'll go over these again in a minute.

### `dnscontrol preview`

```bash
just preview
```

### delete files

```bash
rm dns/zones/*
```

### `dnscontrol preview` again

```bash
just preview
```

### `dnscontrol push`

```bash
just push
```

## just in action

### list just recipes

```bash
just --list
```

but our repo makes it even easier...

```bash
just
```

Probably exit the container because of `podman` permisisons issue.

## container in action

### Run container

```bash
just run_con
```

### Run dig test

```bash
just test_quick
```

### Run go test

```bash
just test_dns
```

```bash
just
```

Mention various choices for tests.

## Feedback desired

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/FEEDBACK.md
```

## Conclusion

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/CONCLUSION.md
```

## Ending card

```bash
glow -w 0 https://raw.githubusercontent.com/chicks-net/presentation-notes/refs/heads/main/fini-coredns-example/ENDING_LINKS.md
```

Maximum ending card length is 20 seconds.  Tell people that the links
will also be in the description.
