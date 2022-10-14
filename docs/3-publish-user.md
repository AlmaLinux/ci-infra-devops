# Publish Images to User Repos 

The third and final job in Container/Docker images jobs list. This job has to run after 
the docker pull request is merged and all default and minimal images are available for public use.

- Uses RootFS files to create container images and publish to docker.io/almalinux and quay.io/almalinuxorg 
## Job Build Options

### Run Environment (`RUNENV`)

- `RUNENV`, Specifies the job environment. Based on this value output publish repo is being used for uploading of the assets

![image](https://user-images.githubusercontent.com/1273137/195866468-5c6a5342-0f59-4918-bfaf-8e9de3848e40.png)

### Image Type to publish (`IMG_TYPE`)

Specifies the type of image to publish. It can be 'ALL, 'UBI' (Micro, Base Init), Official (Default and Minimal)

![image](https://user-images.githubusercontent.com/1273137/195867095-7f4c3191-fdd2-4570-ba94-e8dd7bc60b86.png)

### Os Version (`AL8PUBLISH` or `AL9PUBLISH`) and Publish Branch (`AL8PUBLISH` or `AL9PUBLISH`)

- Publish Version Almalinux 8 or AlmaLinux9.
- Atleast one option should be selected
- Both value can be selected to publish
- When Both field selected `NO`, job will fail
- Selecting `YES` will populate the branch menu.
- Select `YES` in Os Version to publish, it will enable `AL8PUBLISH` or `AL9PUBLISH` and populate its contents

![image](https://user-images.githubusercontent.com/1273137/195870592-41f8a2d6-29ae-4d7b-9daf-18df313409eb.png)

![image](https://user-images.githubusercontent.com/1273137/195870691-5e508e49-3c4e-4be8-9645-987a243f1005.png)

![image](https://user-images.githubusercontent.com/1273137/195870846-9f1f909c-1dc4-48e4-932c-f1adb1d68caf.png)

![image](https://user-images.githubusercontent.com/1273137/195870960-57945442-4163-4cea-9575-679989ce86ca.png)


### Job Summary

Provides the details about the OS version, branch to publish and repo location based on environment.

![image](https://user-images.githubusercontent.com/1273137/195871177-44aec408-39d3-4a9b-abcb-60c839cfa572.png)

![image](https://user-images.githubusercontent.com/1273137/195871274-cf80e11e-96da-4399-b2b5-64587ad5a764.png)

### Full view

![image](https://user-images.githubusercontent.com/1273137/194078930-dbed2952-9411-4d36-9847-6446777b5321.png)


### Sample Run log

![image](https://user-images.githubusercontent.com/1273137/194079036-64385d67-bee6-4704-8eb0-d00cc833085f.png)
