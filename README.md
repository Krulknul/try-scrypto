# try-scrypto

This repository provides a VS Code dev containers configuration with a complimentary Docker image that allows you to quickly try out Scrypto on your machine, without going through all its installation steps.

For an introduction about working inside of dev containers in VS Code, see the [documentation](https://code.visualstudio.com/docs/devcontainers/containers).

This repository includes the basic "hello" example that is generated when a new package is created with `scrypto new-package`. Once you open the project inside the container, you will have the entire Scrypto toolchain available in that isolated environment.

# How to try out scrypto

You will need to have Docker installed, in addition to the Dev containers extension in VS Code. For instructions on their installation, find their respective documentation pages.

1. Clone this repository:

```bash
git clone git@github.com:Krulknul/try-scrypto.git
```

2. Open the directory with VS Code:

```bash
code try-scrypto
```

3. VS Code might suggest you to open the repository in a dev container, because of the existing `.devcontainer` config. If it does, click "Reopen in container". Else, open the command palette and type "Reopen in container". Docker might pull the image if it's not yet present and then start the container.

4. Wait for rust-analyzer to finish checking and indexing. It might take a bit of time before IntelliSense comes alive.

5. Try out Scrypto!

Use `scrypto build` to build the project, or try out `scrypto --help` for more subcommands. Additional CLI tools are also present inside the container, like `resim`, the Radix Engine simulator, or `rtmc` and `rtmd`, the Radix transaction manifest compiler and decompiler respectively.

### Exiting the container

To get out of the container, open the command palette again and type "Reopen Folder Locally", to find the command for that. The code is mounted inside the container, so any changes will be persistent.

### Customizing the image

The dev container is set up to use a Dockerfile, so it is possible to add more development tools to the environment as you wish.


# Using this setup for another project
You can use the dev container here as a full time development environment for your Scrypto projects.
In your project, set up a simple `.devcontainer/devcontainer.json`:
```json
{
    "name": "Scrypto 1.3.0",
    "image": "ghcr.io/Krulknul/scrypto:1.3.0",
    // add some useful extensions you might need
    "customizations": {
        "vscode": {
            "settings": {},
            "extensions": [
                "rust-lang.rust-analyzer",
                "tamasfe.even-better-toml"
            ]
        }
    }
}
```

And voila! Use the instructions above to enter the dev container.
You can extend the image by using your own Dockerfile and starting from the image I published.