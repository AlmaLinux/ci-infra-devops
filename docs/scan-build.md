# Scan for updates and build RootFS

Job has four input params to process.

`INPUT_TAG` `INPUT_TAG` value used as a baseline for security update scanning and build process. 

Possible default values are `almalinux:8` or `almalinux:9`.

For development and test purposes, we can use dated version tags like `almalinux:8.6-20220901` 
or `almalinux:9.0-20220901`

Use `al8` or `al9` for `JOB_TAG`, this is a prefix value used in the creation log and intermediate 
files processing

By design, RootFS files are only created when there are some security package(s) updates found. 
That can be overwritten by setting `FORCE_BUILD_ROOTFS` to true

![image](https://user-images.githubusercontent.com/1273137/194070024-89e5e9a8-2113-485f-95c6-167c0e90ea16.png)


### Sample log output

![image](https://user-images.githubusercontent.com/1273137/194069886-cdef1bb2-3e43-4142-971e-b4e89242e664.png)

