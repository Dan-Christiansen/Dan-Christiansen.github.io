---
title: 'PBS TORQUE'
date: 2022-05-11
permalink: /posts/2022/05/PBS-Torque/
tags:
  - tools
  - HPC
  - computing
  - research
---

PBS TORQUE is a job scheduler and resource manager. There are many good references for how to use PBS TORQUE out there. These are some I have used:

[PBS Professional 12.2 Programmer's Guide](https://wiki.vcu.edu/download/attachments/34801309/PBSProProgramGuide12.2.pdf?version=1&modificationDate=1442463758274&api=v2)

[PBS Professional User's Guide](https://www.auburn.edu/cosam/departments/physics/department/comp-resources/files/pbs/PBSProUserGuide9.1.pdf)

Generally, use a search engine to look up "PBS Professional Guide" and your version of PBS TORQUE.

## Job submission script

## Submit a job
`qsub`

## Delete a job
To delete a single submitted job, `qdel` -p <jobID>

To delete all jobs submitted by a user, `qdel` -u <username>

## Monitor running jobs
`qstat`

## Pause jobs
If a job **hasn't** started yet, you can hold it in the queue with `qhold` <jobID>

To release a job held with `qhold`, use `qrls` <jobID>

To pause all of a specific user's jobs that **haven't** started yet, use `qselect` -u <username> | xargs qhold

If a job is running, you can hold it with `qsig` -s <jobID>

To release a job held by `qsig`, use `qsig` -s resume <jobID>

To pause all of a specific user's jobs that **have** started, use `qselect` -u <username> | xargs qsig -s suspend
