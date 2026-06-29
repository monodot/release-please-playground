# release-please-playground

A small monorepo for testing release-please and Conventional Commits. It has
three components, each released and versioned on its own:

- `runner/` — a Dockerfile. Released as `runner-vX.Y.Z`.
- `frontend/` — a JS project. Released as `frontend-vX.Y.Z`.
- `library/` — a JS project. Released as `library-vX.Y.Z`.

## How releasing works here

1. You merge commits to `main` using Conventional Commit messages, for example
   `feat(frontend): add a button`.
2. The `release-please` workflow reads those messages and opens a release pull
   request for each component that changed. The pull request bumps the version
   file and updates that component's `CHANGELOG.md`.
3. When you merge a release pull request, release-please creates the tag, for
   example `frontend-v1.1.0`, on that same commit.
4. The `publish` workflow triggers on the tag and checks that the version in
   the tag matches the version committed in the repo. This proves the tag and
   the version always agree.

## Setup after cloning

Turn on the commit message hook once:

```
git config core.hooksPath .githooks
```

## Making the publish step fire automatically

A tag that release-please creates with the default `GITHUB_TOKEN` will not
trigger the `publish` workflow. To make it fire, add a personal access token as
a repository secret named `RELEASE_PLEASE_TOKEN`. Without it, you can still test
`publish` by pushing a tag by hand.

## Trying it out

1. Make a change and commit it, for example:
   `git commit -am "feat(frontend): add a greeting"`
2. Push to `main`. Watch the `release-please` workflow open a release pull
   request for `frontend`.
3. Merge that pull request. Watch release-please create the `frontend-v1.1.0`
   tag, and the `publish` workflow confirm the versions match.
