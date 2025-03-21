# animus
[![Build and Test](https://github.com/divy-sh/rdns-resolver-rs/actions/workflows/rust.yml/badge.svg)](https://github.com/divy-sh/rdns-resolver-rs/actions/workflows/rust.yml)
[![License](https://img.shields.io/badge/License-GNU20GPL-blue?style=flat-square)](https://raw.githubusercontent.com/divy-sh/rdns-resolver-rs/master/LICENSE)

# rdns-resolver-rs

A DNS resolver implemented in Rust, designed to handle DNS queries efficiently. This project showcases the power of Rust in building network services with safety, speed, and concurrency.

## Features
- Fast DNS query resolution
- Modular design for easy extension
- Lightweight and memory-efficient
- Written in Rust for performance and safety

## Installation

To build and run this project, you'll need Rust installed. You can install Rust by following the instructions on the [official website](https://www.rust-lang.org/).

Clone the repository:

```bash
git clone https://github.com/divy-sh/rdns-resolver-rs.git
cd rdns-resolver-rs
```

Then, build the project:
```bash
cargo build --release
```

## Usage

Once the build is complete, go to the following directory.
```bash
rdns-resolver-rs/target/release/
```
To start the DNS resolver, run the following command. 
```bash
./rdns_resolver_rs
```
The server will start listening on the port (2053). You can configure the server port by changing the REQ_PORT in utils.rs.

To send a query to the server, run the following command in a new terminal window.
```bash
dig @[IP ADDR] -p [PORT] [www.test.com]
```
## TODO

- Figure out why some of the root name servers don't respond.
- generalize the code by extracting the placeholder configurations out of the code, into a config file.

## Release Notes

### 0.1.1

- Implement concurrency, but since the project was meant for learning how dns resolvers work, it may or may not work properly and may produce unexpected results.
- Add remaining tests for LRU Cache implementation.

### 0.1.2

- Implement DNS name compression
- Fix REFUSED RCODE on querying some addresses that return CNAME.
