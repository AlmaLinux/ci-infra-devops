# Scan for updates and build RootFS

The first job in the container/docker image RootFS file creation process. This job runs in a schedule; check for any security updates released since the last release of the image. AlmaLinux native dnf search and 3rd party grype are used for the security scanning process. When one or more security updates are found, it continues to create RootFS files for publishing the image. We can choose to for the job to create RootFS file even when there are NO new security updates found

## Job Build View

![image](https://user-images.githubusercontent.com/1273137/194070024-89e5e9a8-2113-485f-95c6-167c0e90ea16.png)

## Job Parameters

Job has four input params to process. Two required and two optional

- `INPUT_TAG`, Required field. This field value is used as a baseline for the sofware update security scanning process. 
  - Possible default values are `almalinux:8` or `almalinux:9`.
  - For development and test purposes, we can use dated version tags like `almalinux:8.6-20220901` 
or `almalinux:9.0-20220901`
- `JOB_TAG`, Required field. This field is used for prefix/suffix on the job logs and intermediate files. Use `al8` or `al9`. This way, it will help to identify the input environment 
- `GIT_REPO`, Optional Filed. Location of job `scripts and Dockerfile` templates
- `FORCE_BUILD_ROOTFS`, Optional field. By design, RootFS files are only created when there are some security package(s) updates found. 
That can be overwritten by setting this field to `true`


### Sample log output

![image](https://user-images.githubusercontent.com/1273137/194069886-cdef1bb2-3e43-4142-971e-b4e89242e664.png)

