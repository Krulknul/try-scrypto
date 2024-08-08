# try-scrypto

This repository provides a VS Code dev containers configuration with a complimentary Docker image that allows you to quickly try out Scrypto on your machine, without going through its installation steps.

It includes the basic "hello" example that is generated when a new package is created with `srypto new-package`

# How to use

You will need to have Docker installed, in addition to the Dev containers extension in VS Code. For instructions on their installation, find their respective documentation pages.

1. Clone this repository:

```bash
git clone git@github.com:Krulknul/try-scrypto.git
```

2. Open the directory with VS Code:

```bash
code try-scrypto
```

3. VS Code might suggest you to open the repository in a dev container. If it does, click "Reopen in container". If it doesn't, open the command palette and type "Reopen in container". Docker might pull the image if it's not yet present and start the container.

4. Wait for rust-analyzer to finish checking and indexing.

5. Try out Scrypto!

Use `scrypto build` to build the project, or try out `scrypto --help` for more subcommands. Additional CLI tools are also present inside the container, like `resim`, the Radix Engine simulator, or `rtmc` and `rtmd`, the Radix transaction manifest compiler and decompiler respectively.

### Exiting the container

To get out of the container, open the command palette again and type "Reopen Foler Locally", to find the command for that. The code is mounted inside the container, so any changes will be persistent.

### Customizing the image

The dev container is set up to use a Dockerfile, so it is possible to add more development tools to the environment as you wish.

### More information

For more information about working inside of dev containers in VS Code, see the [documentation](https://code.visualstudio.com/docs/devcontainers/containers).