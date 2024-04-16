# Demo of warnings from `.git_archival.txt` in setuptools-scm

This is a simplified reproduction of the issue https://github.com/pypa/setuptools_scm/issues/987.

## Setup

1. Build yourself a virtualenv to test in:

    ```sh
    $ python -m venv .venv
    $ source .venv/bin/activate
    ```

2. Install `build` to do the builds:

    ```sh
    $ pip install build
    ```


## Run It/Demo the Issue

1. Activate the venv:

    ```sh
    $ source .venv/bin/activate
    ```

2. Do a build:

    ```sh
    $ python -m build .
    ```

    You can uncomment the lines in `MANIFEST.in` to avoid the warning by removing `.git_archival.txt` from the sdist.

    You can also test this with Hatchling instead of Setuptools by commenting/uncommenting the relevant lines at the top of `pyproject.toml`.

3. Clean up the build products before running again:

    ```sh
    $ rm -rf dist src/testpyproj.egg-info src/testpyproj/_version.py
    ```
