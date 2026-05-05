# Signing

APT trust is provided by signing the `Release` metadata, not by individually signing `.deb` files.

Tracked public key:

```text
Identity: SecuGen Connect Packages <packages@secugen.com>
Fingerprint: 1061 A9DE 6A4D 1952 927E 905C C2B3 6AFA A846 F669
Key ID: C2B36AFAA846F669
Expires: 2029-05-04
Public key: gpg.key
```

Signed metadata for the current stable APT repo:

```text
apt/dists/stable/Release
apt/dists/stable/Release.gpg
apt/dists/stable/InRelease
```

The secret key stays in an operator-managed GPG keyring or company-approved signing vault. Do not commit exported secret keys, revocation certificates, keybox files, passphrases, private backups, local key paths, or signing-host inventory to this repository.

Private key backup and restore procedures belong in an internal runbook, not in this public package repository.
