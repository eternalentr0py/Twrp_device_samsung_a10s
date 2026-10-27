# Twrp_device_samsung_a10s (eternalentr0py fork)

TWRP device tree for Samsung Galaxy A10s (SM-A107F / a10s).

## Crypto / FBE

Configured for stock **File-Based Encryption**:

- `fileencryption=aes-256-xts:aes-256-cts:v1` on `/data` in `recovery/root/etc/twrp.fstab`
- `TW_INCLUDE_CRYPTO` / `TW_INCLUDE_CRYPTO_FBE` in `BoardConfig.mk`
- Security patch `2023-03-01` aligned with stock vendor
- DE keys live under `/data/unencrypted/key` (`stretching=nopassword`)

Build via [a10s-twrp-crypto](https://github.com/eternalentr0py/a10s-twrp-crypto) workflow (clones this tree + Trustonic blobs).

## Packing

`bootimg.mk` builds recovery with header v2 and appends `SEANDROIDENFORCE` for Samsung LK. Do not hand-repack the ramdisk if you need a bootable image.
