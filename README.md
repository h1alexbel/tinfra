tinfra - a template for your repository for managing Infrastructure
and Deployments: [Terraform](https://www.terraform.io), and [Rultor](https://rultor.com)
are the instruments employed.

Table of Contents:
* [Terraform Setup](#terraform-setup)
* [Configuring Rultor](#configuring-rultor)
* [Executing Scripts](#executing-scripts)
* [GitHub Actions](#github-actions)
* [Secrets you need to provide](#secrets-you-need-to-provide)
* [Env Variables](#env-variables)

## Terraform Setup

For terraform, we have [src](https://github.com/h1alexbel/tinfra/tree/master/src) directory.
Keep all your `.tf` files inside it.

## Configuring Rultor

[Rultor.com](https://rultor.com) is a Continuous Delivery GitHub-based chatbot.
To configure it use [.rultor.yml](https://github.com/h1alexbel/tinfra/blob/master/.rultor.yml) file inside the root of the repo.

## Executing Scripts

If you need to execute some scripts during the deployment/release
use [scripts](https://github.com/h1alexbel/tinfra/tree/master/scripts) directory.

## GitHub Actions

For GitHub Actions we use `plan` and `apply` terraform commands.
On each Pull Request, GitHub will run [plan action](https://github.com/h1alexbel/tinfra/blob/master/.github/workflows/plan.yml).

Once changes are [approved](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/approving-a-pull-request-with-required-reviews)
[apply action](https://github.com/h1alexbel/tinfra/blob/master/.github/workflows/apply.yml) will be executed.
Modify them to add Cloud-Provider authentication and other specific integrations.

We pack you with an example for GCP.
Check out [.github/examples/gcp](https://github.com/h1alexbel/tinfra/tree/master/.github/examples/gcp).

## Secrets you need to provide

For running this template, you will need at least
these variables be in your [GitHub Secrets](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions):
* `TOKEN`: GitHub token

## Env Variables

If you need to provide some env variables during the deployment/release
use [env](https://github.com/h1alexbel/tinfra/tree/master/env) directory.

## How to Contribute

Fork repository, make changes, send us a [pull request](https://www.yegor256.com/2014/04/15/github-guidelines.html).
We will review your changes and apply them to the `master` branch shortly,
provided they don't violate our quality standards.
