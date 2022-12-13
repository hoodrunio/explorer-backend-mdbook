# Fetch Folder

This [`folder`](https://github.com/testnetrunn/explorer-backend/tree/main/src/fetch) contains files representing categories expect two files.

[`fetch/utils.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/fetch/utils.rs) file contains the definitions of some utility methods.

[`fetch/requests.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/fetch/requests.rs) file contains the definitions of `RPC`/`REST API`/`JSON RPC` request functions.

All the other files represent a category.

And each file/category implements methods to [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct to fetch chain data related to this category.

Any chain specific feature must be handled inside methods using [`match expressions`](https://doc.rust-lang.org/rust-by-example/flow_control/match.html).

For example:

```rs
use crate::chain::Chain;

impl Chain {
    /// Returns the inflation of the chain.
    fn get_inflation(&self) {
        // previous

        // Path can be changed by chain. So we do below.
        let path = match self.inner.name {
            "evmos" => "/evmos/inflation/v1/inflation_rate",
            _ => "/cosmos/mint/v1beta1/inflation",
        };

        // rest
    }
}
```
