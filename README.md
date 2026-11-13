# Skypuff firmware releases

Firmware releases for the Skypuff winch remote. The remotes check for updates here over WiFi and install them themselves. There is no source code in this repository, only releases.

## A release

| File | What |
|---|---|
| `manifest.json`, `manifest.sig` | the release number, the versions and the SHA-256 of every file, signed |
| `board.bin` | the firmware of the remote's board, encrypted: only a Skypuff remote can install it |
| `radio_tx.bin`, `radio_rx.bin` | the firmware of the radio modules |
| `radio_tx-<build>.elf`, `radio_rx-<build>.elf` | the same module firmwares with their debug information, to read the crash logs of the modules; the remotes don't fetch them |

A remote takes the manifest of the latest release, checks its signature and the SHA-256 of every file before installing anything. A changed or replaced file is refused. Mirrors may serve the same files.

## Source code of the GPL parts

The radio modules run [mLRS](https://github.com/olliw42/mLRS), the winch controller runs the [VESC firmware](https://github.com/vedderb/bldc). Both are free software under the GNU General Public License 3.0. The source code of the versions in these releases:

- mLRS: https://github.com/Jeto251/mLRS, branch `skypuff-rp4td-1.4.04`
- VESC firmware: https://github.com/ddosoff/bldc

The licenses of all open source software in the remote are on its screen: Settings → Authors → Open source licenses.
