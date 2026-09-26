# Jenkins Backup and Restore Lab

An infrastructure-learning project that combines Terraform, EC2 bootstrap automation, Jenkins backup files, and a restore workflow.

## Intended workflow

1. Provision an EC2 instance with Terraform.
2. Install Java, Docker, Jenkins, Jenkins CLI, and supporting utilities.
3. Download a Jenkins backup artifact.
4. Restore selected Jenkins configuration.
5. Validate the restored controller.

Relevant Jenkins plugins include:

- [ThinBackup](https://plugins.jenkins.io/thinBackup/)
- [HTTP Request](https://www.jenkins.io/doc/pipeline/steps/http_request/)

## Files

- `main.tf` — infrastructure configuration
- `user_data.sh` — instance bootstrap
- `jenkins_job.txt` — job/pipeline notes
- `JenkinsBackup/` — example backup content

## Important security warning

Jenkins home directories can contain encrypted credentials, controller secrets, user data, plugin binaries, and environment-specific configuration. A public Git repository is not a safe backup destination.

Before reusing this lab:

- Remove all credentials and secret material from Git history.
- Rotate credentials that were ever included in a commit.
- Store backups in encrypted object storage with restricted IAM access.
- Verify restore procedures in an isolated environment.
- Pin and review plugin versions.

> Treat this repository as an educational snapshot, not as a production backup solution.
