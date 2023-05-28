# bleskomat-docs

Source files and scripts needed to build the documentation for Bleskomat products. Uses the open-source project [mdBook](https://rust-lang.github.io/mdBook/index.html) to build html files which can be rendered in a browser.

* [Requirements](#requirements)
* [Development](#development)


## Requirements

* [Rust and Cargo](https://www.rust-lang.org/tools/install)
* [mdBook](https://rust-lang.github.io/mdBook/guide/installation.html)


## Development

Create a new book:
```sh
mdbook init name-of-the-book
```

Serve HTML files:

```sh
mdbook serve --open
```

Build a book's HTML files:
```sh
mdbook build ./bleskomat-bills-atm
```
