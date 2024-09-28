# chicks-net/presentation-notes/just-intro

I want to make a nice intro video about `just`.

## ToC

* [Snippets](./SNIPPETS.md) - copy and paste snippets for the recorded demo
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
  * [ ] Add card for link to https://www.youtube.com/watch?v=hgNN2wOE7lc
  * [ ] Copy description from v1.2
  * [ ] Set languages to US English
  * [ ] Add keywords from v1.2
  * [ ] Edit captions

## Title

So far I like:

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
  * Extracting data from TOML or JSON
  * Creating a pull request
  * Inline Perl or LUA
  * github action
* Conclusion
  * Reduces developer toil without creating new problems.
