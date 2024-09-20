# chicks-net/presentation-notes/just-intro

I want to make a nice intro video about `just`.

## Links

* https://just.systems/man/en/ - the good view of the docs
* https://github.com/casey/just - the git repo for `just`
* casey/just#2357 led to https://www.youtube.com/watch?v=hgNN2wOE7lc
  * Awesome production values
  * Comparison is mostly to Taskfile, which I don’t care about at all.
  * He whines about tabs in source code, this seems silly.

## Title

So far I like:

* Use just to speed development

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
