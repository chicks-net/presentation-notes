# markdownlint notes

## config

```yaml
---
default: True
MD013: False
MD034: False
MD041: False
MD042: False
MD004:
  style: dash
MD010:
  code_blocks: False
```

## rules

- MD004 - ul-style - only dashes please
- MD010 - no-hard-tabs - hard tabs are ok in code blocks
- MD013 - line length - ignored
- MD034 - no-bare-urls - ok for this notes site, but this stays enabled for Hugo sites
- MD041 - first-line-h1 - doesn't make sense in a Hugo site
- MD042 - no-empty-links - copied from example, not sure how helpful this is
