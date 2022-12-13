# Cron Jobs Folder

This [`folder`](https://github.com/testnetrunn/explorer-backend/tree/main/src/cron_jobs) contains files that contain the definitions of methods implemented to [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct.

[`cron_jobs/all.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs) file contains the definition of [`cron_jobs_all`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs#L7) function that spawns a new thread for each cron job.

All the other files are to define cron job methods that will be spawned to new threads and run intermittently inside [`cron_jobs_all`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs#L7) function.
