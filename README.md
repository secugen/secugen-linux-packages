# SecuGen Linux Packages

Package-publication repository for SecuGen Linux artifacts.

This repository backs the public GitHub Pages APT and RPM repositories:

```text
https://secugen.github.io/secugen-linux-packages/gpg.key
https://secugen.github.io/secugen-linux-packages/apt
https://secugen.github.io/secugen-linux-packages/rpm/stable/x86_64
```

Current staged package:

```text
Package: secugen-connect
Version: 0.4.314
Architecture: amd64
Channel: stable
APT path: apt/dists/stable
Package path: apt/pool/main/s/secugen-connect/secugen-connect_0.4.314_amd64.deb
RPM path: rpm/stable/x86_64/secugen-connect-0.4.314.x86_64.rpm
```

First-time setup for Debian/Ubuntu clients:

```bash
curl -LO https://secugen.github.io/secugen-linux-packages/secugen-linux-repo.deb
sudo apt install ./secugen-linux-repo.deb
sudo apt update
sudo apt install secugen-connect
```

After the setup package is installed, normal package updates use:

```bash
sudo apt update
sudo apt install secugen-connect
```

Useful verification:

```bash
apt-cache policy secugen-connect
```

First-time setup for Fedora clients:

```bash
sudo curl -fsSL -o /etc/yum.repos.d/secugen.repo https://secugen.github.io/secugen-linux-packages/secugen.repo
sudo dnf makecache
sudo dnf install secugen-connect
```

After the repo file is installed, normal package updates use:

```bash
sudo dnf makecache
sudo dnf upgrade secugen-connect
```

The setup package installs:

```text
/usr/share/keyrings/secugen-archive-keyring.gpg
/etc/apt/sources.list.d/secugen.list
```

The private GPG signing key must not be committed here. Only the public key at `gpg.key`, signed APT/RPM metadata, package indexes, package files, setup package files, and receipts belong in this repository.
