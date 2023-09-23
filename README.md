# NixOS

A personal installation and configuration guide for Nix and NixOS.

## Description

The information contained in this file is based on the [official documentation](https://nix.dev/) and the [user-maintained wiki](https://nixos.wiki/) as well as the [main page](https://nixos.org/) and the [associated forum](https://discourse.nixos.org/). 

#### Nix

[Nix](https://nixos.org/manual/nix/stable/) is both a programming language and a package manager. Packages are provided via the [Nixpkgs](https://nixos.org/manual/nixpkgs/stable/) collection in the form of **expressions**, which in turn describe build tasks called **derivations**. A derivation can include dependencies, sources, scripts, environment variables or other instructions necessary for building a package. Nix aims to make expressions fully deterministic.

To achieve this goal, several desirable features are implemented:
- Declarative programming paradigm
    - The logic of a computation is described without expressly specifying the necessary sequence of steps, making the control flow entirely implicit. This style is applied to the abstraction of software package management. In contrast, imperative
      programming explicitly states the transformations to be executed.
- Immutable configuration
    - Once a system configuration is built, its composition cannot be changed and will always remain the same for identical input parameters. This greatly reduces the risk for accidental or malicious modifications.
- Functional language
    - Instead of using sequential statements to modify the running state of a program, functions are applied and composed to construct the program directly by mapping input to output values. As first-class citizens, functions support all operations
      available to other entities, meaning they can be assigned to names, taken as arguments or returned by other functions. These properties facilitate the handling of complex problems through the implementation of modular structures. Additionally,
      functions always produce the same result and cannot be affected by any side effects, making the language purely functional. 
- Lazy evaluation
    - Also known as call-by-need, this strategy evaluates expressions only when necessary and avoids repetition by sharing the results.

Individual packages are installed into isolated subdirectories generated through cryptographic hashes inside a parent directory called the **store**. The unique identifier of each package takes into account its name and version, as well as the names and versions of all its dependencies.

This approach allows the simplification of some important tasks:
- Multiple users and versions
    - 
- Atomic upgrades and rollbacks
- Safe reference and garbage collection
- Transparent deployment of source and binary
- Reproducible management of build environments

#### NixOS

[NixOS](https://nixos.org/manual/nixos/stable/) is 

## Installation

The installation procedure is described separately in [this file](https://github.com/frtzzzzz/nixos/blob/main/INSTALL.md).

## Configuration

#### Flakes
