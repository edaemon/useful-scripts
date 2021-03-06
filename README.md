# Useful scripts

This is a collection of some scripts that I've had occasion to use. They're not necessarily "good" or widely usable, but I've used them to get a job done here and there. They're collected here for my reference and safekeeping.

## Basic information

* `cloudflare-log-range` (bash): Downloads the Cloudflare logs for a given time range, even if that time range is longer than one hour. Requires the Cloudflare zone have the Enterprise Log Share enabled and the [logshare utility](https://github.com/cloudflare/logshare) installed. (There is an [open PR](https://github.com/cloudflare/logshare/pull/37) to add this functionality to the utility itself.)
* `git-revert-merges` (bash): Revert all git merges between two commits. Useful for rolling back a large number of merges without altering repository history (as opposed to `git reset`). You may need to adjust your `merge.renameLimit`.
* `multi-ssh` (bash): A basic script to issue a command to multiple hosts via SSH, intended as a quick-and-dirty solution where things like [parallel-ssh](https://github.com/ParallelSSH/parallel-ssh) are not readily available.
* `print-remote-cert` (bash): Print the SSL/TLS certificate found at the remote address. Does not verify the domain/port are reachable.
* `s3-select-json-to-csv` (Python): Convert a file formatted for [AWS S3 SELECT](https://docs.aws.amazon.com/AmazonS3/latest/dev/s3-glacier-select-sql-reference-select.html) (JSON objects, one on each line) to CSV, for use in other contexts.
* `cross-server-du` (bash): Iterate over a list of servers, estimate disk usage at the root level, and consolidate the data. Useful for checking what's taking up all the space in a cluster or environment.
* `github-org-storage` (bash): Print the GitHub Actions/Packages storage used for the 100 most-recently updated repositories belonging to the target GitHub organization.
* `ssmh` (bash): Helper script for AWS Systems Manager SSH sessions. A no-frills profile switcher for the AWS CLI that also retrieves the EC2 instances that are currently
set up for use with AWS Systems Manager Sessions Manager (SSM) and displays basic information about them. This is meant to be used in conjunction with some SSH configuration
which is documented in the script itself.

## Installation

To make these easier to use, you can clone the repo (anywhere) and put the repo in your `PATH`. For example:

```
export PATH="$PATH:$HOME/projects/useful-scripts"
```

That can be a little messy, so I usually add an alias to my `.bashrc` or `.bash_profile` files, e.g.:

```
alias print-remote-cert="~/projects/useful-scripts/print-remote-cert"
alias ssmh="source ~/projects/useful-scripts/ssmh"
```
