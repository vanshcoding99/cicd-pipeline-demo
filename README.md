# CI/CD Pipeline Demo

Class participation activity for COMP 3520 (Software Engineering) at Thompson Rivers University.

A GitHub Actions pipeline that builds, tests and deploys a static page to GitHub Pages.

## Pipeline stages

The workflow lives in `.github/workflows/pipeline.yml` and runs on every push to `main`.

| Stage | What it does |
| --- | --- |
| Build | Copies `index.html` into a `site/` directory and uploads it as a build artifact. |
| Test | Downloads the artifact and checks that `index.html` exists, is not empty, has a valid doctype, has a title, and has balanced `html` tags. |
| Deploy | Publishes the site to GitHub Pages. Runs only if build and test both pass. |

The stages are chained with `needs:`, so a failure in build stops test, and a failure in test stops deploy.

## Live site

https://vanshcoding99.github.io/cicd-pipeline-demo/

## Running it manually

The workflow also has `workflow_dispatch`, so it can be triggered from the Actions tab without pushing a commit.
