# oosexgang PIF

Configuration updates for **oosexgang PIF Updater**.

## Files

| File | Description |
| --- | --- |
| [`pif.json`](pif.json) | Device profile, including model, fingerprint, security patch date, and initial SDK level. |
| [`keybox.xml`](keybox.xml) | Keys and certificate chains consumed by the compatible framework implementation. |
| [`info.txt`](info.txt) | JSON manifest containing the release version and SHA-256 hashes of both configuration files. |

## Updates

The current KernelSU test module checks for updates after boot and every **6 hours**. Failed checks are retried after **5 minutes**.

The updater validates both files and their hashes before activating the complete configuration pair. Previous versions remain available locally. GMS unstable and Play Store restart when the configuration changes.

Active configuration:

```text
/data/local/oosexgang/current/pif.json
/data/local/oosexgang/current/keybox.xml
```

Run a manual update check as root:

```sh
pif-updater
```

A compatible framework implementation is required. This repository distributes configuration data only.

## Publishing an update

1. Update `pif.json`, `keybox.xml`, or both.
2. Recalculate both SHA-256 hashes and update `pif_sha256` and `keybox_sha256` in `info.txt`.
3. Set a new `version`, keep `format: 1`, and publish the changed files together in a single commit to `pif-data`.

## Download URLs

- [info.txt](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/info.txt)
- [pif.json](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/pif.json)
- [keybox.xml](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/keybox.xml)
