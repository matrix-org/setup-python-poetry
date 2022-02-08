This is an action which sets up Python and poetry for a project that uses [Poetry](https://python-poetry.org/) to manage its dependencies.
It requires a `poetry.lock` file to be present in the root of the repository. The action:

- calls [`actions/setup-python`](https://github.com/actions/setup-python),
- `pip`-installs `poetry`,
- `poetry install`-s the current project,
- uses [`actions/cache`](https://github.com/actions/cache) to cache the poetry installation and the virtual environment it manages.

From this point, the caller of the action can run commands within the poetry-managed environment with `poetry run`.

The Python and Poetry versions to are configurable: see `action.yaml` for details.

This particular action is loosely based on [`snok/install-poetry`](https://github.com/snok/install-poetry): in particular, the advice from its README on handling caching.
