# gh-observer features

`gh pr checks --watch` gives you a mute list of check names with no sense of
time.  During the 30-90 seconds that GitHub takes to queue your jobs, you get
to play everyone's favorite guessing game: "is it stuck or just slow?"

`gh-observer` answers the question instead of creating it:

- **Runtime metrics** - shows how long each check has been running, like `3m 52s`, instead of an inscrutable pending dot.
- **Queue latency** - shows how long GitHub sat on a job before starting it, so the queue delay is never mistaken for your problem.
- **Startup phases** - a "Waiting for Actions to start..." message with elapsed seconds instead of a blank screen during GitHub's slow start.
- **Inline error logs** - failed checks print their error lines right in the list, so the first clue does not require a browser.
- **Historical averages** - each job gets an average runtime from recent runs, so `2m` today is normal but `4m` means something is up.
- **Real-time updates** - auto-refreshes every 5 seconds, no manual re-polling.
- **Repo mode** - `--repo` is a persistent dashboard of every active PR and branch run in a repo, with completed checks fading out.
- **Watch by URL** - any PR or Actions run by full URL, even in repos you have never cloned, with GitHub Enterprise hosts supported too.
- **Rate limit backoff** - backs off automatically when approaching API limits, so the watch survives a long CI day.
- **Script friendly** - exit codes (0=success, 1=failure) for pipelines, plus `--quick` for a snapshot without the history fetch.

## Downside

- Live logs for a job that is still running are not possible today because
  the GitHub Actions API only serves logs after a job completes.  If that
  matters to you, upvote
  https://github.com/orgs/community/discussions/154834
- No live logs means a slow job is still just numbers on a screen, but at
  least they are honest numbers with a queue time attached.
