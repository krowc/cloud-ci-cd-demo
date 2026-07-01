![CI Status](https://github.com/krowc/cloud-ci-cd-demo/actions/workflows/main.yml/badge.svg)

# Documentation
- How it Works: The pipeline utilizes an isolated VM (ubuntu-latest) provided by Github. It automatically checks out the codebase, sets up Node.js v18, installs the required dependencies, and executes the automated test suite. Once all the test jobs pass, it then triggers a deployment job to build and publish assets over to Github Pages.
- What Triggers Deployment: The workflow is configurred to listen for Git activity; hence, any changes pushed to the main branch triggers the pipeline. To ensure safety, the deploy job explicitly requires the build-and-test job first to succeed before proceeding.
- Security Setup: The pipeline opeartes under strict write permissions rather than hardcoded sensitive credentials or personal access tokens directly. 
