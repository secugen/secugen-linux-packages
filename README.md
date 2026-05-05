# SecuGen Linux Packages

Package-publication repository for SecuGen Linux artifacts.

This repository backs the public GitHub Pages APT repository:

```text
https://secugen.github.io/secugen-linux-packages/gpg.key
https://secugen.github.io/secugen-linux-packages/apt
```

Current staged package:

```text
Package: secugen-connect
Version: 0.4.307
Architecture: amd64
Channel: stable
APT path: apt/dists/stable
Package path: apt/pool/main/s/secugen-connect/secugen-connect_0.4.307_amd64.deb
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

The setup package installs:

```text
/usr/share/keyrings/secugen-archive-keyring.gpg
/etc/apt/sources.list.d/secugen.list
```

The private GPG signing key must not be committed here. Only the public key at `gpg.key`, signed APT metadata, package indexes, package files, setup package files, and receipts belong in this repository.
