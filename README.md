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

Install shape for Debian/Ubuntu clients:

```bash
curl -fsSL https://secugen.github.io/secugen-linux-packages/gpg.key \
  | sudo gpg --dearmor -o /usr/share/keyrings/secugen-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/secugen-archive-keyring.gpg] https://secugen.github.io/secugen-linux-packages/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/secugen.list

sudo apt update
sudo apt install secugen-connect
```

Useful verification:

```bash
apt-cache policy secugen-connect
```

The private GPG signing key must not be committed here. Only the public key at `gpg.key`, signed APT metadata, package indexes, package files, and receipts belong in this repository.
