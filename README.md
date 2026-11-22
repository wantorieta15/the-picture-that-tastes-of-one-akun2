# Sate Ayam — The picture that tastes of one ingredient

[![make.fun](https://make.fun/badge/the-picture-that-tastes-of-one-20261122-2047.svg)](https://make.fun/bounty/the-picture-that-tastes-of-one-20261122-2047)
[![rank](https://make.fun/badge/the-picture-that-tastes-of-one-20261122-2047/wantorieta15/the-picture-that-tastes-of-one-akun2/rank.svg)](https://make.fun/bounty/the-picture-that-tastes-of-one-20261122-2047)
[![reward](https://make.fun/badge/the-picture-that-tastes-of-one-20261122-2047/wantorieta15/the-picture-that-tastes-of-one-akun2/reward.svg)](https://make.fun/bounty/the-picture-that-tastes-of-one-20261122-2047)

Entry for [The picture that tastes of one ingredient](https://make.fun/bounty/the-picture-that-tastes-of-one-20261122-2047) on make.fun.

One dish, one ingredient you can taste at a glance: three chicken satay
skewers, thick glossy peanut sauce dripping, charred caramelised edges,
smoke curling up, crushed peanuts and a lime wedge on dark slate under a
warm spotlight.

## How it works

`main.py` (Python 3.13, standard library only, no network) copies the
hero image from `assets/` to `$MAKEFUN_OUTPUT_DIR/entry.png` — exactly
1024×1024 pixels, at most 1 MiB — and prints its size and dimensions.

`assets/dish.png` is the single asset the entry ships; there is no
fallback image.

## Output validation

Before finishing, `main.py` verifies its own output and fails loudly
instead of handing the judge a bad file:

- source image exists, otherwise it exits with an error;
- output starts with the official PNG signature
  (`89 50 4E 47 0D 0A 1A 0A`), checked before anything else is read,
  so a corrupt or mislabelled file fails with its actual first bytes
  named in the error;
- output is a readable PNG, exactly 1024×1024, at most 1 MiB;
- SHA-256 of `entry.png` matches the source file byte-for-byte.

On success it prints the dimensions, byte size and the first 16
hex characters of the matching SHA-256.

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out python3 main.py
```
