# chicks-net/presentation-notes/gh-observer-quick

Quick intro to `gh-observer`, the `gh` CLI extension that watches GitHub
Actions like `gh pr checks --watch` wishes it could: runtime metrics, queue
latency, and inline error logs instead of a mute list of pending dots.

The demo runs against a scratch repo (`chicks-net/gh-observer-demo`) built
during the [snippets](./SNIPPETS.md) prep, so the recording never waits on
real work.  These notes are their own PR, merged before recording.

This is also the first demo recorded with [Cap](https://cap.so), so this
directory doubles as my Cap trial run the way the `just` videos were my
Zoom trial run.

## ToC

- Snippets - copy and paste snippets for the recorded demo
  - [Snippets 1](./SNIPPETS.md) - the snippets
- Slides
  - [Opening](./OPENING.md) - title slide
  - [Features](./FEATURES.md) - intro/features slide
  - [Conclusion](./CONCLUSION.md) - closing slide

## Links

- https://github.com/fini-net/gh-observer - the git repo for `gh-observer`
- https://github.com/fini-net/gh-observer#example-animations - real-time example animations from their README
- https://github.com/orgs/community/discussions/154834 - why live job logs are not possible (yet)
- https://cap.so - Cap, the screen recorder for this demo
- https://github.com/CapSoftware/Cap - Cap's git repo

## Recordings

The whole point of this recording is to kick the tires on Cap the same way
I kicked Zoom's tires for the `just` videos.  Zoom surprised me with a clock
overlay and iMovie choked on the odd 1224x810 frames, so the bar for "tool
that mostly stays out of the way" is set.

### Cap setup checklist

- [ ] Install Cap from https://cap.so and grant screen + mic permissions.
- [ ] Do Not Disturb ON so notifications do not photobomb the TUI.
- [ ] Terminal window at 109 col x 37 rows, the size that worked for the `just` videos.
- [ ] Bump the terminal font so the TUI reads at video scale.
- [ ] Cap window capture of just the terminal, not the whole screen.
- [ ] Test recording to verify mic level, resolution, and capture before doing it for real.

### Cap trial notes (fill in while recording)

- Frame resolution produced: ?
- Trim/edit experience: ?
- Instant share link experience: ?
- Export to mp4 for youtube: ?
- Captions: ?

## Title

- gh-observer: stop asking "is my CI stuck or just slow?"
- alternate: Quick intro to watching GitHub Actions with gh-observer

## Outline

- Introduction
- Features
- Demo
  - install the extension
  - open a PR in the demo repo
  - old way, new way
  - break markdownlint on purpose, then fix it
  - repo dashboard, external PR, exit codes
- Conclusion
