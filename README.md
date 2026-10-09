# oosexgang PIF Data

The `pif-data` branch contains the device profile, keybox, and release manifest used for configuration updates.

## Files

| File | Description |
| --- | --- |
| [`pif.json`](pif.json) | Device profile, including model, fingerprint, security patch date, and initial SDK level. |
| [`keybox.xml`](keybox.xml) | Keys and certificate chains. |
| [`info.txt`](info.txt) | JSON release manifest containing `format`, `version`, `model`, `pif_sha256`, and `keybox_sha256`. |

## Publishing an update

1. Update `pif.json`, `keybox.xml`, or both.
2. Recalculate the SHA-256 hashes of both files and update `pif_sha256` and `keybox_sha256` in `info.txt`.
3. Set the release `version` and profile `model`, keeping `format: 1`.
4. Publish the changed data files and manifest together in a single commit to `pif-data`.

The manifest hashes must match the exact contents of the published files.

## Download URLs

- [info.txt](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/info.txt)
- [pif.json](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/pif.json)
- [keybox.xml](https://raw.githubusercontent.com/wannqn/oosexgang-PIF/pif-data/keybox.xml)
