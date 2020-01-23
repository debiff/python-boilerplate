# Python boilerplate

![Build Status](https://img.shields.io/github/workflow/status/debiff/python-boilerplate/Build)
![Top language](https://img.shields.io/github/languages/top/debiff/python-boilerplate)
![Code size](https://img.shields.io/github/repo-size/debiff/python-boilerplate)

This repo is a scaffold to manage a python application. 

It uses a set of local tools to keep the codebase consistent and organized.
It makes use of docker and a docker-compose to build and run the application in a clean environment. 

It includes also a CI github action workflow to ensure that all the conventions are respected.

The creation of this repo is highly inspired by:

- https://x-team.com/blog/keep-your-local-machine-clean-with-docker-2/
- https://blog.jerrycodes.com/pre-commit-is-awesome/
- https://sourcery.ai/blog/python-best-practices/
- https://dan.yeaw.me/posts/github-actions-automate-your-python-development-workflow/

## Motivation

It's always time consuming to set up linting and static type checking in a project, so I created this boilerplate with the tool that I always use in my projects.

## Installation

- [x] Poetry
- [x] Docker
- [x] Pre-commit
- [x] Github Action

First of all if you don't have it yet install [poetry](https://github.com/python-poetry/poetry).

```bash
pip install --user poetry
```

Use Poetry to install all the dependencies of the project in a virtual environment automatically created.

```bash
cd python-boilerplate
poetry install
```

In order to make the hook works activate the virtualenv and create the hook file with [pre-commit](https://pre-commit.com/):

```bash
poetry shell
pre-commit install
```
## Usage

Put your code in the src directory and your tests in the tests directory.

Everytime you commit the pre-commit hook starts.
You can add new check, lint or whatever you want in ***.pre-commit-config.yaml***.

If you want to add another step when commit insert in the stages filed the value ***commit***, if you want to execute the tool in
the ci workflow insert ***manual***
```yaml
- repo: https://github.com/humitos/mirrors-autoflake
  rev: v1.1
  hooks:
    - id: autoflake
      args: ['--check --in-place', '--remove-all-unused-imports', '--remove-unused-variable']
      stages: [manual]
```
## Contributing
Please read [CONTRIBUTING.md] for details on our code of conduct, and the process for submitting pull requests.

## License
[MIT](https://choosealicense.com/licenses/mit/)