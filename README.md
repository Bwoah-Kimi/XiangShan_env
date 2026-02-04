# xs-env (legacy Nanhu 2024)

This superproject tracks a legacy Nanhu-era XiangShan setup with local 2024 config presets consolidated into the XiangShan submodule.
The original superproject README is preserved as `ORIGINAL_README.md`.

## Submodules and branches

- `XiangShan` -> fork branch `nanhu-legacy-2024`
- `XiangShan-southlake` -> fork branch `southlake-legacy-2024`
- `verilator`, `NEMU`, `DRAMsim3`, `NutShell`, `nexus-am` -> upstream

Initialize:

```
git submodule update --init --recursive
```

## What was added in XiangShan

See `XiangShan/README.md` for full details. In short, the legacy branch adds:

- `MyMinimalSmallConfig` (small core + small caches)
- `MyMinimalMidConfig` (mid-size core + larger TLBs, BPD on)
- `NoL2Config` (L2 disabled; L3 connects to L1 clients)
- helper scripts under `XiangShan/scripts/`

Note: `XiangShan/build.sc` uses a fixed JVM heap (default `-Xmx15G`).
If RTL generation OOMs, raise `-Xmx` before running `make verilog`.

## What was added in XiangShan-southlake

The southlake legacy branch contains a `MyMinimalConfig` preset and related build/scalafmt tweaks (commit `e67ddf3f` in that submodule).
It is kept separately because southlake tracks a different upstream branch.

## Original README

See `ORIGINAL_README.md` for the original project description and links.
