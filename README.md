# dependency-gate-workflow

The workflow file that an organisation ruleset runs on every pull request as the dependency gate.

It lives in a public repository so that the gate can also run on public repositories. It contains no logic and no secrets: it creates a short-lived GitHub App token from credentials held in the calling repository's organisation, checks out the gate's code from a private repository with that token, and runs it.

- `.github/workflows/dependency-gate.yml` is the only file that matters. Changes to it run in every repository in the organisation, so they need a reviewed pull request.
- The gate's rules, tests and documentation are in the private gate repository.
