# NixOS

A personal installation and configuration guide for Nix and NixOS.

## Description

The information contained in this file is based on the [official documentation](https://nix.dev/) and the [user-maintained wiki](https://nixos.wiki/) as well as the [main page](https://nixos.org/) and the [associated forum](https://discourse.nixos.org/). 

#### Nix

[Nix](https://nixos.org/manual/nix/stable/) is both a programming language and a package manager. Packages are provided via the [Nixpkgs](https://nixos.org/manual/nixpkgs/stable/) collection in the form of **expressions**, which in turn describe build tasks called **derivations**. A derivation can include dependencies, sources, scripts, environment variables or other instructions necessary for building a package. Nix aims to make expressions fully deterministic.

Some of the desirable features characterising the project can be summed up as follows:
- Declarative
- Pure
- Functional
- Lazy

This approach allows the simplification of several important tasks:
- Multiple users and versions
- Atomic upgrades and rollbacks
- Garbage collection
- Transparent deployment of source and binary

#### NixOS

[NixOS](https://nixos.org/manual/nixos/stable/) is 

## Installation

The installation procedure is described separately in [this file](https://github.com/frtzzzzz/nixos/blob/main/INSTALL.md).

## Configuration

#### Flakes
