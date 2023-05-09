# go-serverless-sam-template

[![Go](https://github.com/go-micah/go-serverless-sam-template/actions/workflows/go.yml/badge.svg?branch=main)](https://github.com/go-micah/go-serverless-sam-template/actions/workflows/go.yml)

## Overview

This repository is a template and starting point for building a serverless application, written in Go, and designed to be deployed to AWS with the Serverless Application Model (SAM). The repository is meant to cover the following areas:

1. Local development using GitHub Codespaces
2. Local development with Go and SAM
3. Deployment with SAM
4. Deployment with GitHub Actions and SAM Pipelines

## Local development using GitHub Codespaces

This repository contains a **devcontainer** with the following packages:

- AWS CLI
- AWS SAM CLI
- Docker in Docker

This means that you can clone this repo and use it as the basis for a development environment with GitHub Codespaces and it will install the tools listed above automatically.


## Local development with Go and SAM

The code structure in this repo is designed to allow you to use `go mod` from the root of the project to manage your Go dependencies. This means you may choose to set up your project at a **package** with a top level package file in the root, or you can add sub-folders to taste.

For Lambda functions or CLI programs, I'v chosen to keep these in the `cmd` folder with a separate folder for each function under `cmd/functions`. This makes it easy to separate out the package code from the Lambda function code or any CLI code you may wish to develop.

With SAM you can reference the function code easily in the [template.yml](template.yaml) by adding the path and handler as follows:

```
CodeUri: cmd/functions/hello
Handler: bootstrap
```

> Please note that in the example above, I am using `bootsrap` as the Handler since I am working with the `provided.al2` runtime.

## Deployment with SAM

More to come on this soon ...

- sam deploy
- profiles and bootstrapping

## Deployment with GitHub Actions and SAM Pipelines

More to come in this soon ...

- Environments
- sam pipelinne init
- access keys and IAM
- go build vs. sam build
