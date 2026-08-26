# pup-check

<img
src="./images/pup.png"
alt="pup logo"
width="110">

`pup-check` checks a Python repository for deterministic internal consistency.
It compares related repository declarations and structure and reports
inconsistencies.

## Purpose

Professional Python repositories contain declarations and structures that
should agree with one another.
Examples include:

- project and package names
- `src/` package structure
- `pyproject.toml` metadata
- command-line entry points
- Python module paths

Small inconsistencies can remain unnoticed until a command, build, test,
documentation workflow, or release fails.

`pup-check` performs deterministic checks for internal repository consistency
and reports detected problems.

## Check a Repository

```shell
uvx pup-check
```

A successful check returns exit code `0`.
A failed consistency check returns a nonzero exit code and reports the
detected problem.

## Checks

This release checks:

- `pyproject.toml` exists
- `pyproject.toml` can be read and identifies the project
- a Python package can be detected when a `src/` layout is present
- modules referenced by `[project.scripts]` entry points exist

## See Also

- [API](./api.md)
