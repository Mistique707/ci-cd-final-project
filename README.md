# CI/CD Tools and Practices Final Project

**Project name:** `ci-cd-final-project`
**Repository:** https://github.com/Mistique707/ci-cd-final-project

A Python Flask counter microservice with a complete CI/CD pipeline. GitHub Actions runs linting (flake8) and unit tests (nose) on every push and pull request to `main`. A Tekton pipeline on OpenShift cleans up the workspace, clones the repository, lints, runs the unit tests, builds the image with buildah and deploys the application.

## Project structure

| Path | Purpose |
|------|---------|
| `service/` | Flask counter microservice |
| `tests/` | Unit tests (nose) |
| `.github/workflows/workflow.yml` | GitHub Actions CI workflow: Lint with flake8, Run unit tests with nose |
| `.tekton/tasks.yml` | Tekton tasks: `cleanup` and `nose` (Run unit tests with nose) |
| `.tekton/flake8.yml` | Tekton task: `flake8` |
| `.tekton/pipeline.yml` | Tekton pipeline: cleanup, git-clone, flake8, nose, buildah, deploy |

## Setup

After entering the lab environment you will need to run the `setup.sh` script in the `./bin` folder to install the prerequisite software.

```bash
bash bin/setup.sh
```

Then you must exit the shell and start a new one for the Python virtual environment to be activated.

```bash
exit
```

## License

Licensed under the Apache License. See [LICENSE](/LICENSE)

## Author

Skills Network

## <h3 align="center"> © IBM Corporation 2023. All rights reserved. <h3/>
