# Python Flask - Demo Web Application

This is a simple Python Flask web application. The app provides system information and a realtime monitoring screen with dials showing CPU, memory, IO and process information.

The app has been designed with cloud native demos & containers in mind, in order to provide a real working application for deployment, something more than "hello-world" but with the minimum of pre-reqs. It is not intended as a complete example of a fully functioning architecture or complex software design.

Typical uses would be deployment to demos of Docker, CI/CD (build pipelines are provided), deployment to Ubuntu server (digital ocean).

## Screenshot

![screen](https://user-images.githubusercontent.com/14982936/30533171-db17fccc-9c4f-11e7-8862-eb8c148fedea.png)




## Building & Running Locally

### Pre-reqs

- Be using Linux, WSL or MacOS, with bash, make etc
- [Python 3.11+](https://www.python.org/downloads/) - for running locally, linting, running tests etc
- [Docker](https://docs.docker.com/get-docker/) - for running as a container, or image build and push
- Ubuntu server


### Makefile

A standard GNU Make file is provided to help with running and building locally.

```text
help                 ๐ฌ This help message
lint                 ๐ Lint & format, will not fix but sets exit code on error
lint-fix             ๐ Lint & format, will try to fix errors and modify code
image                ๐จ Build container image from Dockerfile
push                 ๐ค Push container image to registry
run                  ๐ Run the server locally using Python & Flask
deploy               ๐ Deploy to Azure Web App
undeploy             ๐ Remove from Azure
test                 ๐ฏ Unit tests for Flask app
test-report          ๐ฏ Unit tests for Flask app (with report output)
test-api             ๐ฆ Run integration API tests, server must be running
clean                ๐งน Clean up project
```

Make file variables and default values, pass these in when calling `make`, e.g. `make image IMAGE_REPO=blah/foo`

| Makefile Variable | Default                |
| ----------------- | ---------------------- |
| IMAGE_REG         | ghcr<span>.</span>io   |
| IMAGE_REPO        | benc-uk/python-demoapp |
| IMAGE_TAG         | latest                 |
| AZURE_RES_GROUP   | temp-demoapps          |
| AZURE_REGION      | uksouth                |
| AZURE_SITE_NAME   | pythonapp-{git-sha}    |

The app runs under Flask and listens on port 5000 by default, this can be changed with the `PORT` environmental variable.




