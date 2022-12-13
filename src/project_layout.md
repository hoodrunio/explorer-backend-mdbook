# Project Layout

## Build Script

[`build.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/build.rs) file in the project directory is the build script that runs before compilation.

It reads the chains inside [`Chains.yml`](https://github.com/testnetrunn/explorer-backend/blob/main/Chains.yml) file. And generates code for [`state.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs) file.

## Chains Configuration File

[`Chains.yml`](https://github.com/testnetrunn/explorer-backend/blob/main/Chains.yml) file is the configuration file for chains support.

It uses a YAML-like syntax, but is specialized for this use case.

## Chain File

[`chain.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs) file contains the definition of [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct that has methods to work with any Cosmos based blockchain.

## Macros File

[`macros.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/macros.rs) file contains the definitions of macros.

It only has [`init_chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/macros.rs#L3) macro currently.

## Main File

[`main.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/main.rs) file is the entry of the application.

It runs [`start_web_server`](https://github.com/testnetrunn/explorer-backend/blob/c2634d0d89bfb420670d0a1383be63b9c26ead70/src/server.rs#L9) function to start the application.

## Server File

[`server.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs) file contains the definition of [`start_web_server`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs#L9) function that starts the application.

## State File

[`state.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs) file is generated automatically by the [build script](/project_layout.html#build-script).

It contains the definition of [`State`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L7) struct, and implementation of a few methods.

[`State`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L7) struct
is the state of the application.

## Utils File

[`utils.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/utils.rs) file contains the definitions of some utility functions.

## Fetch Folder

[`fetch/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/fetch) folder contains files that provide methods to fetch any data for a chain.

All the fetching methods must be implemented to [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct.

Any chain specific feature should be handled inside those fetching methods.

## Database Folder

[`database/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/database) folder contains files that represent data types that will be stored in the database.

But [`database_tr.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/database/database_tr.rs) file contains the definition of [`DatabaseTR`](https://github.com/testnetrunn/explorer-backend/blob/main/src/database/database_tr.rs#L10) struct and implements methods to get/save data easily while hiding the logic.

All the other files in the folder are representing a specific data type that will be stored in the database.

## Cron Jobs Folder

[`cron_jobs/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/cron_jobs) folder contains files that represent methods implemented to [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct.

Those methods fetch up to date data and save them to database.

All the methods should be spawned in new threads to run intermittently.

There is a specific file for spawning methods, called [`all.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs).

Those methods are spawned in loops with their intervals inside [`cron_jobs_all`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs#L7) function.

And [`cron_jobs_all`](https://github.com/testnetrunn/explorer-backend/blob/main/src/cron_jobs/all.rs#L7) function must only be called at once while initializing the HTTP server.

## Routes Folder

[`routes/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/routes) folder contains files that contain functions that represent endpoints of a specific category.

Each file contains functions for the endpoints in a category.

Each function is an endpoint.

Each function must be added as a service of HTTP server in [`server.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs#L40) file to create its endpoint.

## Read Only Old In-Memory Database Folder

[`read_only_old_in_memory_database/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/read_only_old_in_memory_database) folder is previously used in the backend app, but not used currently.

It still exists to help you understand how it worked in the past.
