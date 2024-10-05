# chicks-net/presentation-notes/just-intro

I want to make a nice intro video about `just`.

## ToC

* Snippets - copy and paste snippets for the recorded demo
  * [Snippets 1](./SNIPPETS.md) - the snippets used for the [youtube](https://youtu.be/m7ZCnGnYyvs?si=QNvUZJiGo20FVdnD)
  * [Snippets 2](./SNIPPETS2.md) - the snippets used for subsequent live demos
* Slides
  * [Opening](./OPENING.md) - title slide
  * [Features](./FEATURES.md) - intro/features slide
  * [Conclusion](./CONCLUSION.md) - closing slide

## Links

* https://just.systems/man/en/ - the good view of the docs
* https://github.com/casey/just - the git repo for `just`
* casey/just#2357 led to https://www.youtube.com/watch?v=hgNN2wOE7lc
  * Awesome production values
  * Comparison is mostly to Taskfile, which I don’t care about at all.
  * He whines about tabs in source code, this seems silly.

## Recordings

I had 3 practice sessions in private repos before recording with these public repos:

* https://github.com/chicks-net/just-demo1
  * Zoom overlaid a clock and my delivery was very weak so I didn't try to edit the video.
  * I was pleased with how easy Zoom made it to share the video with all partipants in the call.
  * The [Conclusion slide](./CONCLUSION.md) didn't fit well in the terminal window during recording.
  * Played with the window size and ended up with 109 col x 37 rows which caused odd 1224x810 frame resolution.
* `v1.2` Friday -- https://github.com/chicks-net/just-demo2
  * Fixed Zoom clock issue.  The setting lives in the client **and** in the cloud interface.
  * My delivery was acceptable, but I skipped a few things and ~20s needed to get edited out.
  * I tried editing in iMovie, but it doesn't look like it was happy with the 1224x810 frame resolution.
  * The youtube studio editor worked for clipping.
  * I also tried to add annotations for the docs link and the other video
* `v1.3` Saturday -- https://github.com/chicks-net/just-demo3
  * Let's try to not get lost or forget much or this will be another dress rehearsal....
  * [x] Add card for link to https://www.youtube.com/watch?v=hgNN2wOE7lc
    * I wanted to make the card stay up longer, but I couldn't find an option for that.
  * [x] Copy description from v1.2
  * [x] Set languages to US English
  * [x] Add keywords from v1.2
  * [x] Edit captions (aka subtitles)
  * [x] Set category to "Science & Technology".
  * [x] Edit out initial dead air. (4s)
  * [x] Pick thumbnail
  * [x] Picked https://www.youtube.com/playlist?list=PLj1L6ffGFWPvMJL57qmMZ1ntcdS2h6xwa as first item for end screen.
  * [x] Picked https://youtu.be/3-Jrp6it9Ss?si=G_IL3xUgMcvk2L9X as second item for end screen.
  * [x] ↪ Add end screen.
  * [x] Add chapters
  * [x] Verify end screen after it is public.
  * [x] Post comment on [github issue](https://github.com/casey/just/issues/2357).
  * [x] Post comment in other video since replies are not a feature of youtube anymore.
  * Sorry for all of the coughs and "ums".

## Title

I went with:

* Using just to speed development

## Outline

* Introduction
* Features
  * Doesn’t require YAML, XML, or JSON.
  * Agnostic about tabs versus spaces.
  * Support any scripting language of your choice.
  * Run the same code locally or in a github action
  * Just scripting looks very similar to shell scripting, but the defaults are safer.
* Demo
  * Changing directories or not
  * Make-like dependencies
  * Documenting recipes
  * Tabs or spaces are fine
  * Extracting data from TOML
  * Creating a pull request
  * Inline Perl or LUA
  * github action
* Conclusion
  * Reduces developer toil without creating new problems.
