# AlmaLinux Infra Docs

All of AlmaLinux production jobs are grouped in one folder for better access.

![image](https://user-images.githubusercontent.com/1273137/194068337-34122bec-4ac8-4582-83ea-623792d2a289.png)

## Container/Documentaion

`Container/Docker images` contains jobs related to building container images.

- [`Scan for Security Updates and Build RootFS`](scan-build.md). The first job to run in a scheduler or On-demand, as needed. Performs security scan updates for AlmaLinux container images. When security updates are found, it generates RootFS files to make an official release.
- [`Create Pull Request with DockerHub`](dockerhub-pr.md). The second job is to run the series. Uses RootFS files are generated in the prior step, generate change log, and create a pull request with the official docker hub library.
- [`Publish Images to User Repos`](publish-user.md). The third and final job is to run the series. Uses RootFS files to create container images and publish to docker.io/almalinux and quay.io/almalinuxorg This job has to run after the docker pull request is merged and all default and minimal images are available for public use.
