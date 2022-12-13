# Chain File

[`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct is defined in [`chain.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs) file.

[`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct represents a Cosmos based chain, and has methods implemented to work with the blockchain.

[`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct is just a [`ChainConfig`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L19) wrapped in an [`Arc pointer`](https://doc.rust-lang.org/std/sync/struct.Arc.html) inside.

Most of the work is done by implementing new methods.
