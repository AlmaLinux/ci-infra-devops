# Create Pull Request with DockerHub

This is the second job run after when any new RootFS file is created from the prior step. 
This job has the ability to generate change-log by comparing new image created in this process 
and the INPUT_TAG. It also setup necessary git branches required to for publishing RootFS files, 
and create a pull request with the official docker hub library. Complete content of the PR is 
automatically crated.

https://github.com/docker-library/official-images/pull/13267

This is one of very critical job, has number of safety measure built-in to avoid accidental overwrite 
of existing production branches

- Job will check for atleast one of AlmaLinux version (8 or 9) has updated RootFs files
- The input RootFS Git branch option menue is dynamically generated to avoid any manual entry
- `BRANCH_LOG` fields gives the job summary prior to run
- `COMMIT_LOG` gives the ability to add any additional custom message to generated pull request


![image](https://user-images.githubusercontent.com/1273137/194076343-527e0f6a-d026-425c-adba-c849073d3ef8.png)


### Sample run log

![image](https://user-images.githubusercontent.com/1273137/194076484-d8436046-f3f3-4220-8e3c-62fca1d1d5ac.png)
