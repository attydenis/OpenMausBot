# Upstream provenance

- **Project:** OpenMausBot
- **Canonical upstream:** `https://github.com/milind-soni/OpenMausBot`
- **Upstream default branch:** `main`
- **Pinned upstream commit:** `87d8a797daffb71b125809dcb6b147d31d69262f`
- **Upstream release at snapshot time:** `v0.1.176`
- **Snapshot date:** November 22, 2026
- **Destination:** `https://github.com/attydenis/OpenMausBot`

## Scope

This is a source snapshot of the complete redistributable open-source edition. It is not presented as an official upstream fork and does not claim ownership of upstream code, names, artwork, or trademarks.

The upstream `enterprise/` directory contained 10 tracked files and is the only upstream source directory intentionally excluded. Its license says that the directory may not be redistributed. Upstream expressly states that deleting `enterprise/` leaves the ordinary open-source edition, licensed under Apache License 2.0.

The upstream Git history was also intentionally excluded because it contains the non-redistributable `enterprise/` objects. This repository begins with a clean snapshot commit so those restricted historical objects are not published.

The complete upstream GitHub Actions definitions are preserved byte-for-byte under `.github/upstream-workflows-disabled/` instead of the active `.github/workflows/` path. This prevents unreviewed third-party workflows from running automatically in this repository and avoids requiring elevated GitHub workflow authorization. Review them before restoring them to `.github/workflows/`.

No release binaries, local dependencies, generated packages, credentials, conversations, user configuration, or local application state are included.

## Licensing

The preserved open-source edition is distributed under the upstream Apache License 2.0, subject to the upstream `LICENSE`, `NOTICE`, `LICENSING.md`, third-party notices, and dependency licenses. The OpenMausBot and MausBot names and mascot are upstream trademarks; the Apache License does not grant trademark rights.

Future synchronization must again exclude `enterprise/` unless the copyright holder grants written redistribution permission.
