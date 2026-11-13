# fanme releases

Signed and notarized builds of [fanme](https://fanme.appsurd.lol), a small menu-bar utility for the Mac that shows temperatures and applies calm, progressive fan cooling.

This repository holds release files only: the disk images, their SHA-256 checksums and the release notes. The source code is not public. The website is <https://fanme.appsurd.lol>.

- **Download:** from the website; the link points to the newest release.
- **Requirements:** macOS 14 or later, Apple Silicon only (no Intel).
- **Updates:** fanme checks <https://fanme.appsurd.lol/updates/appcast.xml> and asks before installing anything.

Releases are immutable: a fixed build gets a new build number rather than replacing files. Every file is signed with Developer ID (team `5QVM5Y9RYP`) and notarized by Apple. To check a download:

```bash
shasum -a 256 fanme-*.dmg   # compare with SHA256SUMS.txt in the same release
spctl -a -vv -t open --context context:primary-signature fanme-*.dmg
```
