tinfra - a template for your repository for managing Infrastructure
and Deployments: [Terraform](), [Docker](), and [Rultor]()
are the instruments we employed.

Table of Contents:
* [Terraform Setup](#terraform-setup)
* [Configuring Rultor](#configuring-rultor)
* [Executing Scripts](#executing-scripts)
* [GitHub Actions](#github-actions)
* [Env Variables](#env-variables)

## Terraform Setup

For terraform, we have [src]() directory.
Keep all your `.tf` files inside it.

## Configuring Rultor

[Rultor.com]() is a Continuous Delivery GitHub-based chatbot.
To configure it use [.rultor.yml]() file inside the root of the repo.

## Executing Scripts

If you need to execute some scripts during the deployment/release
use [scripts]() directory.

## GitHub Actions

For GitHub Actions we use `plan` and `apply` terraform commands.
On each Pull Request, GitHub will run [plan action]().

Once changes are [approved]() [apply action]() will be executed.
Modify them to add Cloud-Provider authentication and other specific integrations.

We pack you with an example for GCP.
Check out [.github/examples/gcp]().

## GitHub Secrets

For running this template, you will need at least
these variables be in your GitHub Secrets:
* `TOKEN`: GitHub token

## Env Variables

If you need to provide some env variables during the deployment/release
use [env]() directory.

## How to Contribute

Fork repository, make changes, send us a [pull request](https://www.yegor256.com/2014/04/15/github-guidelines.html).
We will review your changes and apply them to the `master` branch shortly,
provided they don't violate our quality standards.
