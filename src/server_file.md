# Server File

It is at [`server.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs) file.

It contains the definition of [`start_web_server`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs#L9) function which is the entry of the application.

Inside [`start_web_server`](https://github.com/testnetrunn/explorer-backend/blob/main/src/server.rs#L9) function, we create a [`State`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L7) for the application, run cron jobs of all the chains, and create an HTTP server.
