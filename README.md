# actions_python_mypy
A Github action for python static type checking with mypy.


<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Examples:

```
on: [push]

jobs:
  mypy:
    runs-on: ubuntu-latest
    name: "mypy"
    steps:
      - uses: davidslusser/actions_python_mypy@v1.0.0
```
<br/>

```
on: [push]

jobs:
  mypy:
    runs-on: ubuntu-latest
    name: "mypy"
    steps:
      - uses: davidslusser/actions_python_mypy@v1.0.0
        with:
          src: "src"
          options: "--cov=src"
          pip_install_command: "pip install -e .[dev]"
          python_version: "3.9"
```


<br/>

## Inputs
  - **src:** source directory of code to check (defaults to "`.`")
  - **options:** optional flags/parameters used in mypy command
  - **pip_install_command:** pip install command (defaults to "`pip install mypy`")
   - **python_version:** version of python to run workflow with (defaults to "`3.x`")


<br/>

## References
 - https://mypy.readthedocs.io/en/stable/
 - https://pypi.org/project/mypy/