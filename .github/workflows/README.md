# Workflows

## add-labels-standardized.yaml

When issues are opened,
this action adds appropriate labels to the issue.
(e.g. "triage", "customer-submission")

- [Add Labels Standardized GitHub Action]
  - Uses: [senzing-factory/build-resources/.../add-labels-to-issue.yaml]

## add-to-project-garage-dependabot.yaml

When a Dependabot Pull Request (PR) is made against `main` branch,
this action adds the PR to the "Garage" project board as "In Progress".

- [Add to Project Garage Dependabot GitHub Action]
  - Uses: [senzing-factory/build-resources/.../add-to-project-dependabot.yaml]

## add-to-project-garage.yaml

When an issue is created,
this action adds the issue to the "Garage" board as "Backlog".

- [Add to Project Garage GitHub Action]
  - Uses: [senzing-factory/build-resources/.../add-to-project.yaml]

## bandit.yaml

When a Pull Request (PR) is made against `main` branch,
this action runs [Bandit] to detect security issues.

- [bandit.yaml]
  - Uses: [lukehinds/bandit-action]

## black.yaml

When a change is committed to GitHub or a Pull Request is made against the `main` branch,
this action runs the [Black] code formatter.

- [black.yaml]

## dependabot-approve-and-merge.yaml

When a Dependabot Pull Request (PR) is made against the `main` branch,
this action determines if it should be automatically approved and merged into the `main` branch.
Once this action occurs [move-pr-to-done-dependabot.yaml] moves the PR on the "Garage" project board to "Done".

- [Dependabot Approve and Merge GitHub Action]
  - Uses: [senzing-factory/build-resources/.../dependabot-approve-and-merge.yaml]

## dependency-scan.yaml

When a Pull Request is made against the `main` branch,
this action runs [Fast Python Vulnerability Scanner] and [pip-audit].

- [dependency-scan.yaml]
  - Uses:
    - [Fast Python Vulnerability Scanner]
    - [pypa/gh-action-pip-audit]

## flake8.yaml

When a change is committed to GitHub or a Pull Request is made against the `main` branch,
this action runs [flake8] for Python style enforcement.

- [flake8.yaml]
  - Uses: [py-actions/flake8]

## isort.yaml

When a change is committed to GitHub or a Pull Request is made against the `main` branch,
this action runs [isort] to sort the Python import statements

- [isort.yaml]
  - Uses: [isort/isort-action]

## lint-workflows.yaml

When a change is committed to GitHub or a Pull Request is made against the `main` branch,
this action runs [super-linter] to run multiple linters against the code.

- [Lint Workflows GitHub Action]
  - Configuration:
    - [.checkov.yaml]
    - [.jscpd.json]
    - [.yaml-lint.yml]
  - Uses: [senzing-factory/build-resources/.../lint-workflows.yaml]

## move-pr-to-done-dependabot.yaml

When a Pull Request is merged into the `main` branch,
this action moves the PR on the "Garage" project board to "Done".

- [Move PR to Done Dependabot GitHub Action]
  - Uses: [senzing-factory/build-resources/.../move-pr-to-done-dependabot.yaml]

## mypy.yaml

When a change is committed to GitHub or a Pull Request is made against the `main` branch,
this action runs [mypy] to perform static type checking.

- [mypy.yaml]

## pylint.yaml

When a change is committed to GitHub,
this action runs [pylint] to perform static code analysis.

- [pylint.yaml]
