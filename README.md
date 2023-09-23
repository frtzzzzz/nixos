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
    - Also known as call-by-need, this strategy evaluates expressions only when necessary and avoids repetition by sharing the results as required.

Individual packages are installed into isolated subdirectories generated through cryptographic hashes inside a parent directory called the **store**. The unique identifier of each package takes into account its name and version, as well as the names and versions of all its dependencies.

This approach allows for the simplification of some important tasks:
- Multiple users and versions
    - Different versions of the same package are handled separately, avoiding any interference or dependency conflicts. At the same time, non-privileged users can securely install the same software through individual profiles without duplication.
- Atomic upgrades and rollbacks
    - Upgrading packages does not overwrite the previous install and instead adds a different path for the new version. Thanks to this, there exists no point in time at which files from different software versions appear simultaneously. As long as
      the old package is stored, rolling back also remains an option.
- Safe reference and garbage collection
    - The environment tracks references automatically, allowing unused packages to be deleted safely. Additionally, uninstalling software does not directly remove it from the system, enabling rollbacks and keeping different user profiles intact.
      Actual deletions only occur when running the *garbage collector*.
- Transparent deployment of source and binary
    - Expressions generally contain instructions for building a package from source. This process tends to be computationally expensive, as many dependencies may need to be built as well. To avoid this issue, the package manager
      can automatically skip the build process by checking for the existence of *precompiled binaries* and fetching those instead of building locally if possible.
- Reproducible management of build environments
    - Due to all relevant information being stored in a configuration file, environments can easily be replicated on any compatible system.

#### NixOS

[NixOS](https://nixos.org/manual/nixos/stable/) is a Linux distribution based on the package management system Nix.

## Installation

The installation procedure is described separately in [this file](https://github.com/frtzzzzz/nixos/blob/main/INSTALL.md).

## Configuration

#### Commands

#### Flakes
