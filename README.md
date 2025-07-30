# Proto Plugins

A collection of YAML-based plugins for [Moonrepo Proto](https://moonrepo.dev/docs/proto), a multi-language version
manager.

## What is Proto?

[Proto](https://moonrepo.dev/docs/proto) is a multi-language version manager developed by Moonrepo. It helps developers
manage and install different versions of programming languages, package managers, and CLI tools across projects.

## What are these plugins?

These are non-WASM plugins for Proto, defined in YAML format. Non-WASM plugins are simple configuration files that
describe how a tool should be installed and invoked. They're designed for simple and common use cases, particularly CLI
tools.

Each plugin defines:

- The tool's name and type
- How to resolve the tool's version
- Platform-specific configurations
- Installation instructions

## Available Plugins

This repository contains the following plugins:

- **abigen** - A tool from the Ethereum Go implementation for generating Go bindings from Solidity contracts
- **gofumpt** - A stricter formatter for Go code
- **pyoxidizer** - A utility for packaging Python applications
- **solc** - The Solidity compiler for Ethereum smart contracts

## How to Use These Plugins

### Prerequisites

1. Install Proto by following the [official installation guide](https://moonrepo.dev/docs/proto/install)

### Using a Plugin

1. Create a `.prototools` file in your project root if you don't already have one
2. Add the tool and desired version to your `.prototools` file
3. Configure Proto to use the plugin from this repository

Example `.prototools` file:

```toml
solc = "0.8.20"

[plugins]
solc = "https://raw.githubusercontent.com/xurvan/proto-plugins/master/plugins/solc.yml"
```

## Contributing

Contributions are welcome! If you'd like to add a new plugin or improve an existing one:

1. Fork this repository
2. Create a new YAML file in the `plugins` directory or modify an existing one
3. Follow the [non-WASM plugin format](https://moonrepo.dev/docs/proto/non-wasm-plugin)
4. Submit a pull request

## License

This project is licensed under the Apache License, Version 2.0 - see the [LICENSE](LICENSE) file for details.