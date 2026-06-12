# Nutorch Homebrew Tap

GPU tensor daemon and CLI for any shell — Apple-silicon MPS, PyTorch-powered.
See [nutorch/nutorch](https://github.com/nutorch/nutorch).

## Install

```bash
brew tap nutorch/nutorch
brew trust nutorch/nutorch   # brew 6.0+ requires trusting third-party taps
brew install nutorch
```

Then, from any shell:

```bash
torch tensor '[1, 2]' | torch add $(torch tensor '[3, 4]') | torch value
# [4.0, 6.0]
```

## Requirements

- Apple silicon (arm64) — every tensor lives on the GPU via MPS
- macOS

The formula vendors the four LibTorch dylibs nutorch needs (~220MB keg),
extracted from the official PyTorch 2.11.0 wheel on PyPI. Bottles are attached
to [GitHub Releases](https://github.com/nutorch/homebrew-nutorch/releases) on
this repository; without a matching bottle, `brew` builds from the source
tarball (needs Rust, ~1 minute).
