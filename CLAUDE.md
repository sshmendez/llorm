# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`llorm` is an innovative SQLx-based ORM for Rust that uses Large Language Models to generate SQL statements from natural language descriptions in procedural macros. The core concept is to allow developers to specify database operations in plain English within trait functions, which are then converted to SQL via LLM API calls.

## Architecture

### Core Components

1. **Procedural Macros**: The main interface where developers write natural language descriptions of database operations
2. **LLM Integration**: API calls to language models that convert natural language to SQL
3. **SQLx Integration**: Backend database execution using SQLx
4. **SQL Caching System**: Temporary file-based caching with user override capabilities
5. **Code Generation**: Automatic generation of Rust code from LLM-generated SQL

### Design Principles

- **Natural Language First**: Database operations are described in plain English within procedural macros
- **Type Safety**: Generated code maintains Rust's type safety through struct-based input/output matching
- **User Override**: Developers can manually edit generated SQL when needed
- **Flexible Caching**: Hash-based caching with bypass flags for user-edited content

### Key Features

- Procedural macros in trait functions for natural language operation specification
- Automatic SQL generation via LLM API integration
- Struct-based input/output type matching for generated functions
- Temporary file system similar to `sqlx prepare` for SQL caching
- User editing capabilities with `user_edited` flags to bypass cache validation
- Hash-based cache invalidation system

## Common Commands

- **Build**: `cargo build`
- **Run tests**: `cargo test`
- **Check code**: `cargo check`
- **Format code**: `cargo fmt`
- **Lint code**: `cargo clippy`
- **Expand macros**: `cargo expand` (requires cargo-expand)

## Development Notes

- The project will heavily rely on procedural macros, so understanding Rust's macro system is essential
- LLM API integration will require careful error handling and fallback mechanisms
- SQL generation must be validated and sanitized for security
- The caching system should be robust to handle concurrent access and cache invalidation

## Project Planning

See [TODO.md](TODO.md) for the complete development roadmap and task breakdown.