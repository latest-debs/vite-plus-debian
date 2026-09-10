![vite-plus for Debian](.github/readme-header.png)

# vite-plus for Debian

[![Release](https://img.shields.io/github/v/release/latest-debs/vite-plus-debian)](https://github.com/latest-debs/vite-plus-debian/releases)
[![Build](https://github.com/latest-debs/vite-plus-debian/actions/workflows/release.yml/badge.svg)](../../actions)

[Vite+](https://viteplus.dev) — the unified toolchain for the web, behind the
`vp` CLI — packaged for Debian as part of
[latest-debs](https://github.com/latest-debs).

Want your own project packaged and maintained this way? See the
[latest-debs packaging service](https://github.com/latest-debs/apt-repo/blob/main/SERVICE.md).

## Install

Via the latest-debs apt repository:

```sh
sudo apt install extrepo  # if not already installed
sudo extrepo enable latest-debs
sudo apt update
sudo apt install vite-plus
```

Or download a `.deb` from the [Releases](https://github.com/latest-debs/vite-plus-debian/releases) page:

```sh
sudo apt install ./vite-plus_*.deb
```

## Verify

```sh
apt-cache policy vite-plus
vite-plus --version
```

## Supported distributions & architectures

- Debian Bookworm (12), Trixie (13), Forky (14/testing), Sid (unstable)
- amd64, arm64
  (Vite+'s upstream releases only publish amd64/arm64 Linux binaries)

## Notes

- This package installs the global `vp` CLI. The per-project `vite-plus` npm
  package and managed Node.js runtime are handled by `vp` itself.
- Vite+ is currently in beta (voidzero-dev/vite-plus).

## Building

Run the [Build vite-plus for Debian](../../actions) workflow on GitHub with the
desired upstream version. Packaging is driven by
[debian-multiarch-builder](https://github.com/ranjithrajv/debian-multiarch-builder).

## Collaborate with us

latest-debs is a community effort. If you rely on this package and want to
help keep it fresh, watching for a new upstream release or fixing a build
hiccup, we'd love your help. Open an issue on this repo, or email
**latest-debs@users.noreply.github.com** to get involved.

## Disclaimer

Unofficial, volunteer-run packaging — **best-effort, no SLA**.

- **Update cadence:** publishing a release normally triggers an immediate
  apt-repo rebuild via webhook; the ~6h scheduled run is the fallback. GitHub
  outages, a missing trigger token, rate limits, or upstream archive changes
  can delay or skip an update; there is no freshness guarantee.
- **Draft releases:** every build is published as a *draft* that a maintainer
  reviews before promoting, so a new version can lag its build.

For issues with vite-plus itself, see
[voidzero-dev/vite-plus](https://github.com/voidzero-dev/vite-plus).

## License

Packaging scripts in this repo are MIT-licensed. The packaged binaries
remain under their upstream license (`MIT` — see
[voidzero-dev/vite-plus](https://github.com/voidzero-dev/vite-plus)).
