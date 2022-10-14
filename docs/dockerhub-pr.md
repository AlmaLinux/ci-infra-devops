# Create Pull Request with DockerHub

The second job in the Container/Docker automation. This has to run after when any new RootFS file is created from the scan and build step. 
This job has the ability to generate change-log by comparing new image created in this process 
and the INPUT_TAG. It also setup necessary git branches required to for publishing RootFS files, 
and create a pull request with the official docker hub library. Complete content of the PR is 
automatically crated.

https://github.com/docker-library/official-images/pull/13267

This is one of very critical job, has number of safety measure built-in to avoid accidental overwrite 
of existing production branches

## Build Requirements

### `NOFAIL` Option
- When production branch already exists, job will fail to recreate but reuse. In case existing production branch has issues, it has to removed or renamed, so that this pipeline will create new set of branches. Use `NO_FAIL` to true for reusing exisitng production branch.

![image](https://user-images.githubusercontent.com/1273137/195861377-34038eb8-fbb2-4dc7-a4c0-c51b8040f32d.png)


### OS Version to publish

- Use `AL8OPTION` or `AL9OPTION` Option menu to select for processing
- When `AL8OPTION` and `AL9OPTION` choosen as `No Changes`, job will exit since there is nothing to publish.
- Job will check for atleast one of AlmaLinux version (8 or 9) has `Get Branches` selected for updated RootFs files.

![image](https://user-images.githubusercontent.com/1273137/195861545-cbcea1c3-02d9-49aa-a07e-c09fe73758e4.png)

![image](https://user-images.githubusercontent.com/1273137/195861593-c5b52c8b-64e1-459f-9c4c-2093ed64d2f0.png)

### Branches to publish

- The input RootFS Git branch options menu is dynamically generated to avoid any manual entry.  Both `AL8BRANCH` and `AL9BRANCH` are populated using https://github.com/almalinuxautobot/docker-images repo for option menu.

![image](https://user-images.githubusercontent.com/1273137/195861889-6c6cc27a-566f-477d-b961-e67d32b8d96d.png)

![image](https://user-images.githubusercontent.com/1273137/195861818-f99c6127-235c-41f1-ad08-a9f235a1f698.png)

### Job Summary

- `BRANCH_LOG` fields gives the job summary prior to run
- `COMMIT_LOG` gives the ability to add any additional custom message to generated pull request

![image](https://user-images.githubusercontent.com/1273137/195861716-579d25b5-a66c-4962-a882-db1c9fa29365.png)


### Full View
![image](https://user-images.githubusercontent.com/1273137/195858193-02e13b77-42b7-4260-b324-e3506c2d268f.png)


### Sample run log

![image](https://user-images.githubusercontent.com/1273137/194076484-d8436046-f3f3-4220-8e3c-62fca1d1d5ac.png)
