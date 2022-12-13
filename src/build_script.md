# Build Script

The build script is at [`build.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/build.rs).

It runs before the compilation process to generate code automatically.

It generates code for [`state.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs) file reading the chains defined inside [`Chains.yml`](https://github.com/testnetrunn/explorer-backend/blob/main/Chains.yml) file.

It also makes requests to nodes to generate values of some keys for the chains defined in [`Chains.yml`](https://github.com/testnetrunn/explorer-backend/blob/main/Chains.yml) file.

If you find a good way to add support for new chains while the program is running, you can get rid of code generation for [`state.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs) file.
