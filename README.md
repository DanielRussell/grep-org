Like `grep` for a GitHub organization

Given a pattern, GitHub organization, and file path, look through all
of that organization's repos and return matching lines.  Uses the
GitHub API -- no cloning.  Useful for "what apps are using this
vulnerable package" types of searches.

## Installation

You must have a [Personal Access Token
(PAT)](https://github.com/settings/tokens) with at least `repo` scope.

Place this PAT in a file named `.github_credentials_repo.json` in your
home directory, formatted like:

```
{ "user": "my-github-username", "token": "ghp_....." }
```

Run `bundle install` to install necesary gems.

## Usage

Does Linus mention Linux?

```
bundle exec grep-org torvalds README Linux
```

Find `octocat` in all of the `github` organization's READMEs:

```
bundle exec grep-org github README.md octocat
```

Look for [suspicious versions of `coa`](https://www.bleepingcomputer.com/news/security/popular-coa-npm-library-hijacked-to-steal-user-passwords/)

```
bundle exec grep-org my-org yarn.lock 'coa[@:]'
```
