<div align="center">

<img src="snap/gui/dbdelve.png" alt="DBDelve logo" width="128" />

# DBDelve

**A fast, native, multi-engine database client.**

[![dbdelve](https://snapcraft.io/dbdelve/badge.svg)](https://snapcraft.io/dbdelve)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [DBDelve](https://github.com/ShayanAbbas1/dbdelve), a desktop application for browsing databases, running queries and editing data.

</div>

---

## Getting Started

<a href="https://snapcraft.io/dbdelve"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install dbdelve
sudo snap connect dbdelve:password-manager-service
dbdelve
```

Launch from the terminal or your application menu. A desktop keyring is required to save and reuse connection passwords.

## Configure

Manage database connections and preferences in the app. There are no `snap set` options.

| Optional access | Command |
| --- | --- |
| SSH keys and configuration in `~/.ssh` | `sudo snap connect dbdelve:ssh-keys` |
| Databases and exports on removable storage | `sudo snap connect dbdelve:removable-media` |

SSH tunnels use the bundled OpenSSH client. Newly trusted host keys are stored in `~/snap/dbdelve/common/ssh/known_hosts`; existing host keys in `~/.ssh/known_hosts` are also read when connected.

## Limitations

- Use TCP for database servers; host Unix sockets outside accessible directories are restricted.
- SSH tunnels require key authentication. Host SSH agents, hardware tokens and host `ProxyCommand` programs are not supported. The snap sets its own `UserKnownHostsFile` paths.
- Existing settings from native DBDelve, DBeaver and editor installations are not discovered automatically. Import files explicitly from an accessible folder.
- Application updates are managed by snapd.

## Build

```bash
git clone https://github.com/sidalit/dbdelve-snap.git
cd dbdelve-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/dbdelve-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/ShayanAbbas1/dbdelve/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/dbdelve-snap/blob/main/LICENSE).
