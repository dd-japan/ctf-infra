## What's this
This repository contains guides and configuration files of CTFd server, which is able to host on Google Cloud Run.

## Google Cloud Architecture w/ CTFd
We use Cloud Run as a CTFd container server, Cloud SQL as a database and Cloud Storage FUSE as an image upload folder.

![CTFd_Google_Cloud](https://github.com/user-attachments/assets/836883dd-8279-4c0a-ba04-b826bbee67ec)

## CTFd server configuration
CTFd documentation has the [configuration page](https://docs.ctfd.io/docs/deployment/configuration/).

## Datadog employees
If you are using Datadog Sandbox project, our sandbox has the guardrail: [Domain restricted sharing](https://cloud.google.com/resource-manager/docs/organization-policy/domain-restricted-sharing?hl=ja).

As a workaround, add a tag that adapts to the guardrail's exclusion rules: `external-access:allowed` in the case of Allowing unauthenticated Cloud Run invocations.
