# Useful bash scripts

This is a collection of some scripts that I've had occasion to use. They're not necessarily "good" or widely usable, but I've used them to get a job done here and there. They're collected here for my reference and safekeeping.

## Basic information

* `cloudflare-log-range`: Downloads the Cloudflare logs for a given time range, even if that time range is longer than one hour. Requires the Cloudflare zone have the Enterprise Log Share enabled and the [logshare utility](https://github.com/cloudflare/logshare) installed. (There is an [open PR](https://github.com/cloudflare/logshare/pull/37) to add this functionality to the utility itself.)
* `git-revert-merges`: Revert all git merges between two commits. Useful for rolling back a large number of merges without altering repository history (as opposed to `git reset`). You may need to adjust your `merge.renameLimit`.
* `multi-ssh`: A basic script to issue a command to multiple hosts via SSH, intended as a quick-and-dirty solution where things like `[parallel-ssh](https://github.com/ParallelSSH/parallel-ssh)` are not readily available.

## Installation

To make these easier to use, I clone the repo (anywhere) and put the repo in my `PATH`. For example:

```
export PATH=$PATH:~/projects/bash-useful-scripts
```

