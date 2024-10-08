# Overview

[LocalStack](https://localstack.cloud) is a cloud service emulator that runs in a single container on your laptop or in your CI environment. With LocalStack, you can run your AWS applications or Lambdas entirely on your local machine without connecting to a remote cloud provider! Whether you are testing complex CDK applications or Terraform configurations, or just beginning to learn about AWS services, LocalStack helps speed up and simplify your testing and development workflow.

LocalStack supports a growing number of AWS services, like AWS Lambda, S3, Dynamodb, Kinesis, SQS, SNS, and many more! The [Pro version of LocalStack](https://localstack.cloud/pricing) supports additional APIs and advanced features. You can find a comprehensive list of supported APIs on our [☑️ Feature Coverage](https://docs.localstack.cloud/user-guide/aws/feature-coverage/) page.

LocalStack also provides additional features to make your life as a cloud developer easier! Check out LocalStack's [User Guides](https://docs.localstack.cloud/user-guide/) for more information.

## Install

The quickest way get started with LocalStack is by using the LocalStack CLI. It enables you to start and manage the LocalStack Docker container directly through your command line. Ensure that your machine has a functional [`docker` environment](https://docs.docker.com/get-docker/) installed before proceeding.

### Brew (macOS or Linux with Homebrew)

Install the LocalStack CLI through our [official LocalStack Brew Tap](https://github.com/localstack/homebrew-tap):

```bash
brew install localstack/tap/localstack-cli
```

### Binary download (MacOS, Linux, Windows)

If Brew is not installed on your machine, you can download the pre-built LocalStack CLI binary directly:

- Visit [localstack/localstack-cli](https://github.com/localstack/localstack-cli/releases/latest) and download the latest release for your platform.
- Extract the downloaded archive to a directory included in your `PATH` variable:
  - For MacOS/Linux, use the command: `sudo tar xvzf ~/Downloads/localstack-cli-*-darwin-*-onefile.tar.gz -C /usr/local/bin`

### PyPI (MacOS, Linux, Windows)

LocalStack is developed using Python. To install the LocalStack CLI using `pip`, run the following command:

```bash
python3 -m pip install localstack
```

The `localstack-cli` installation enables you to run the Docker image containing the LocalStack runtime. To interact with the local AWS services, you need to install the `awslocal` CLI separately. For installation guidelines, refer to the [`awslocal` documentation](https://docs.localstack.cloud/user-guide/integrations/aws-cli/#localstack-aws-cli-awslocal).

> **Important**: Do not use `sudo` or run as `root` user. LocalStack must be installed and started entirely under a local non-root user. If you have problems with permissions in macOS High Sierra, install with `pip install --user localstack`

## Quickstart

Start LocalStack inside a Docker container by running:

```bash
 % localstack start -d

     __                     _______ __             __
    / /   ____  _________ _/ / ___// /_____ ______/ /__
   / /   / __ \/ ___/ __ `/ /\__ \/ __/ __ `/ ___/ //_/
  / /___/ /_/ / /__/ /_/ / /___/ / /_/ /_/ / /__/ ,<
 /_____/\____/\___/\__,_/_//____/\__/\__,_/\___/_/|_|

 💻 LocalStack CLI 3.6.0
 👤 Profile: default

[12:47:13] starting LocalStack in Docker mode 🐳                       localstack.py:494
           preparing environment                                       bootstrap.py:1240
           configuring container                                       bootstrap.py:1248
           starting container                                          bootstrap.py:1258
[12:47:15] detaching                                                   bootstrap.py:1262
```

You can query the status of respective services on LocalStack by running:

```bash
% localstack status services
┏━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━┓
┃ Service                  ┃ Status      ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━┩
│ acm                      │ ✔ available │
│ apigateway               │ ✔ available │
│ cloudformation           │ ✔ available │
│ cloudwatch               │ ✔ available │
│ config                   │ ✔ available │
│ dynamodb                 │ ✔ available │
...
```

To use SQS, a fully managed distributed message queuing service, on LocalStack, run:

```shell
% awslocal sqs create-queue --queue-name sample-queue
{
    "QueueUrl": "http://sqs.us-east-1.localhost.localstack.cloud:4566/000000000000/sample-queue"
}
```

Learn more about [LocalStack AWS services](https://docs.localstack.cloud/references/coverage/) and using them with LocalStack's `awslocal` CLI.

## Running

You can run LocalStack through the following options:

- [LocalStack CLI](https://docs.localstack.cloud/getting-started/installation/#localstack-cli)
- [Docker](https://docs.localstack.cloud/getting-started/installation/#docker)
- [Docker Compose](https://docs.localstack.cloud/getting-started/installation/#docker-compose)
- [Helm](https://docs.localstack.cloud/getting-started/installation/#helm)

## Usage

To start using LocalStack, check out our [documentation](https://docs.localstack.cloud).

- [LocalStack Configuration](https://docs.localstack.cloud/references/configuration/)
- [LocalStack in CI](https://docs.localstack.cloud/user-guide/ci/)
- [LocalStack Integrations](https://docs.localstack.cloud/user-guide/integrations/)
- [LocalStack Tools](https://docs.localstack.cloud/user-guide/tools/)
- [Understanding LocalStack](https://docs.localstack.cloud/references/)
- [Frequently Asked Questions](https://docs.localstack.cloud/getting-started/faq/)

To use LocalStack with a graphical user interface, you can use the following UI clients:

* [LocalStack Web Application](https://app.localstack.cloud)
* [LocalStack Desktop](https://docs.localstack.cloud/user-guide/tools/localstack-desktop/)
* [LocalStack Docker Extension](https://docs.localstack.cloud/user-guide/tools/localstack-docker-extension/)

## Releases

Please refer to [GitHub releases](https://github.com/localstack/localstack/releases) to see the complete list of changes for each release. For extended release notes, please refer to the [LocalStack Discuss](https://discuss.localstack.cloud/c/announcement/5).

## Contributing

If you are interested in contributing to LocalStack:

- Start by reading our [contributing guide].

- Navigate our codebase and [open issues](https://github.com/localstack/localstack/issues).

We are thankful for all the contributions and feedback we receive.

## Get in touch

Get in touch with the LocalStack Team to
report 🐞 [issues](https://github.com/localstack/localstack/issues/new/choose),
upvote 👍 [feature requests](https://github.com/localstack/localstack/issues?q=is%3Aissue+is%3Aopen+sort%3Areactions-%2B1-desc+),
🙋🏽 ask [support questions](https://docs.localstack.cloud/getting-started/help-and-support/),
or 🗣️ discuss local cloud development:

- [LocalStack Slack Community](https://localstack.cloud/contact/)
- [LocalStack Discussion Page](https://discuss.localstack.cloud/)
- [LocalStack GitHub Issue tracker](https://github.com/localstack/localstack/issues)

### Contributors

We are thankful to all the people who have contributed to this project.

<a href="https://github.com/localstack/localstack/graphs/contributors"><img src="https://opencollective.com/localstack/contributors.svg?width=890" /></a>

### Backers

We are also grateful to all our backers who have donated to the project. You can become a backer on [Open Collective](https://opencollective.com/localstack#backer).


### Sponsors

You can also support this project by becoming a sponsor on [Open Collective](https://opencollective.com/localstack#sponsor). Your logo will show up here along with a link to your website.


## License

Copyright (c) 2017-2024 LocalStack maintainers and contributors.

Copyright (c) 2016 Atlassian and others.

This version of LocalStack is released under the Apache License, Version 2.0 (see [LICENSE](LICENSE.txt)). By downloading and using this software you agree to the [End-User License Agreement (EULA)](docs/end_user_license_agreement).
