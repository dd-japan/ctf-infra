## What's this
This repository contains guides and configuration files of CTFd server, which is able to host on Google Cloud Run.
And also including terraform code for swagstore GKE cluster, CTFd Cloud Run and datastores, and Datadog settings.

## CTFd server architecture
### CTFd on AWS(v1.0)

#### Single EC2 architecture
![image](https://github.com/user-attachments/assets/6ef5a435-fac9-43a4-86a3-a060664b1efe)

### Datadog employees
If you are in Datadog Sandbox AWS account, it has the limitation: AWS Config automatically delete extensive security group rules.

### CTFd on Google Cloud(v2.0)
Use Cloud Run as a CTFd container server, Cloud SQL as a database and Cloud Storage FUSE as an image upload folder.

If there are many CTFd users, which are more than 10, Cloud Run are recommended to be scaled out. 
CTFd server has the login cache locally in a container w/o a Redis server. Redis server is necessary to avoid 403 error due to this.

#### Single container architecture
![image](https://github.com/user-attachments/assets/f6ec4e1b-d65a-43dc-ab51-6437845d899b)

#### Multiple container architecture
![image](https://github.com/user-attachments/assets/6fafed9e-8aa7-4dcf-bd70-ef4ef77cd9f9)

### CTFd server configuration
CTFd documentation has the [configuration page](https://docs.ctfd.io/docs/deployment/configuration/).

### Datadog employees
If you are in Datadog Sandbox GCproject, it has the guardrail: [Domain restricted sharing](https://cloud.google.com/resource-manager/docs/organization-policy/domain-restricted-sharing?hl=ja).

As a workaround, add a tag that adapts to the guardrail's exclusion rules: `external-access:allowed` in the case of Allowing unauthenticated Cloud Run invocations.
