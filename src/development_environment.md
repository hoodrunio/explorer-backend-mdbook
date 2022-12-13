# Development Environment

To prepare your development environment, you need to use a POSIX compatible operating system like [Ubuntu](https://ubuntu.com/download/desktop), [Mac OS](https://www.apple.com/tr/macos/ventura/), [WSL](https://learn.microsoft.com/en-us/windows/wsl/install).

## Installations

You need to install [`Rust language Toolchain`](https://www.rust-lang.org/tools/install).

Run the command below to install it.

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

You also need to install the database program used in the backend app. (It is [`MongoDB`](https://www.mongodb.com/docs/manual/installation/) for now).

You will also need to install [`Docker`](https://docs.docker.com/get-docker/) in the future, after integrating it with the backend app.

## Dependencies

You need some packages to compile programs.

For example you have to install [`build-essential`](https://packages.ubuntu.com/jammy/devel/build-essential) package in Ubuntu.
