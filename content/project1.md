+++
title = "Rust CLI Binary With SQLite"
date = "2023-10-17"
description = "Data Engineering Individual Project 1"
+++

This project delivers a comprehensive Data Extraction, Transformation, Loading (ETL) tool, alongside Querying (CRUD) capabilities, all developed using Rust. The process entails initializing a new Rust project with `cargo init` and installing Rust dependencies through `Cargo.toml` using `cargo build`. Notably, Github Copilot was employed to aid the transition from Python to Rust. This conversion was meticulously crafted to ensure adherence to Rust's syntax, robust error handling, and full utilization of Rust's unique features. 

This toolkit offers a suite of functions for ETL operations on datasets, facilitating queries on a SQLite database. It comprehensively covers CRUD (Create, Read, Update, Delete) operations, logging all queries to a Markdown file, query_log.md, to aid in the tracking and analysis of executed commands.

The operational workflow includes running a Makefile to perform tasks such as installation (`make install`), testing (`make test`), code formatting (`make format`) with Python Black, linting (`make lint`) with Ruff, and an all-inclusive task (`make all`). This automation streamlines the data analysis process and enhances code quality.

To cap it off, the project produces an optimized Rust binary, which is available as a GitHub Actions artifact, ready for download.

Here is my [Demo Video](https://youtu.be/vwk7wgY9qcU) showing a clear, concise walkthrough and demonstration of my CLI binary.

Here is my [Rust CLI Binary With SQLite](https://github.com/nogibjj/tinayiluo_Rust_CLI_Binary_With_SQLite.git) Github project repository. 

