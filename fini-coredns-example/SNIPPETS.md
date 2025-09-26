# just intro snippets

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
podman run -it ubuntu:24.04 bash -c "apt update && apt install -y gh && bash"
```

TODO: how we deal with github authentication?

### Clone repo

```bash
gh repo clone fini-net/fini-coredns-example
```

```bash
cd fini-coredns-example
```

### View code for defining domains

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
