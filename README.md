# C++ Nix Project Template

This is a simple template for C++ projects using Nix and CMake.

## Setup

To enter the development environment, use:

```sh
nix develop
```

This will provide all necessary dependencies for compiling and running the project.

## Building the Project

To build the project, run:

```sh
nix build
```

This will create an executable in the `result/bin/` directory.

## Setting Up LSP for Neovim

For `clangd` in Neovim to correctly detect the compile commands, you need to link the `compile_commands.json` file after building:

```sh
ln -s result/compile_commands.json ./
```

This ensures that LSP features like autocomplete and error checking work properly.

## Project Structure

```
.
├── compile_commands.json -> result/compile_commands.json  # Symlink for LSP support
├── flake.lock         # Lockfile for dependencies
├── flake.nix          # Nix configuration
├── LICENSE            # License file
├── README.md          # Project documentation
├── result -> /nix/store/...-cpp-nix-app  # Build output
└── src
    ├── CMakeLists.txt # CMake build configuration
    └── main.cpp       # Main source file
```

## Notes
- This template assumes a NixOS or Nix-enabled environment.
- You can customize `flake.nix` for additional dependencies as needed.
- The `compile_commands.json` symlink is needed for Neovim's `clangd` to function correctly.

