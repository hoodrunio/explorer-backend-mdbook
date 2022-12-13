# Routes Folder

This [`folder`](https://github.com/testnetrunn/explorer-backend/tree/main/src/routes) contains files that represent categories.

Each file/category contains functions that represent an endpoint.

An example function that represent inflation endpoint:

```rs
#[get("{chain}/inflation")]
pub async fn inflation(path: Path<String>, chains: Data<State>) -> impl Responder {
    let chain = path.into_inner();

    Json(match chains.get(&chain) {
        Ok(chain) => Response::Success(chain.get_inflation_rate().await),
        Err(err) => Response::Error(err),
    })
}
```

Let's continue line by line.

## Endpoint Macro

The macro below defines the path of the endpoint. It is defined as `example.com/{chain}/inflation`. It might be `/axelar/inflation`.

```rs
#[get("{chain}/inflation")]
```

## Defining Function

The function below takes a [`Path`](https://docs.rs/actix-web/latest/actix_web/web/struct.Path.html) and [`Data`](https://docs.rs/actix-web/latest/actix_web/web/struct.Data.html) parameter. They are provided by [`actix-web`](https://crates.io/crates/actix-web). 

[`Path`](https://docs.rs/actix-web/latest/actix_web/web/struct.Path.html) represents path parameters. It is only `{chain}` for this endpoint.

[`Data`](https://docs.rs/actix-web/latest/actix_web/web/struct.Data.html) represents the state of the HTTP server. In this case, it is [`State`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L7) struct.

```rs
pub async fn inflation(path: Path<String>, chains: Data<State>) -> impl Responder {
```

## Extracting Path Params
Path parameters can only be extracted by calling `into_inner()` method.
```rs 
let chain = path.into_inner()
```

## Serializing JSON
`Json(T)` struct converts the data inside to JSON string.
```rs
Json(...)
```

## Getting Chain By Name
We try to get a [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7) struct by using [`get`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L97) method of [`State`](https://github.com/testnetrunn/explorer-backend/blob/main/src/state.rs#L7) struct.

```rs
chains.get(&chain)
```

## Matching Chain
If we successfully get a [`Chain`](https://github.com/testnetrunn/explorer-backend/blob/main/src/chain.rs#L7), we call the method implemented inside [`fetch/`](https://github.com/testnetrunn/explorer-backend/tree/main/src/fetch) folder, and return an enum.

```rs
match chains.get(&chain) {
    Ok(chain) => Response::Success(chain.get_inflation_rate().await),
    Err(err) => Response::Error(err),
}
```