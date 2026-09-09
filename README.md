# gha-e2e-basic

A dedicated, public test repository for running the same GitHub Actions workflow
on GitHub and Buildkite. It contains no application secrets or customer code.

`Representative CI` runs on pushes to `main`, pull requests targeting `main`, and
manual GitHub Actions dispatch. It checks out the real repository, runs the
duration formatter tests on Node 20 and 22, and runs a dependent completion job
only when both matrix jobs succeed. No package installation is required.

Run locally with Node 20 or later:

```sh
npm test
```

The Buildkite connection is provisioned through the normal GitHub Actions
pipeline onboarding flow, not by storing a Buildkite token in GitHub Actions.
GitHub's native workflow runs remain enabled as an independent comparison.
