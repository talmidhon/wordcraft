# RTL visual review evidence — 2026-10-15

Source commit: [`76b01f623326dcd485d76d13822ef06b3e6a0181`](https://github.com/talmidhon/wordcraft/commit/76b01f623326dcd485d76d13822ef06b3e6a0181). Source tree: `336d1f5d384413437664ab3c5847f32294dc17c0`.

These 22 original WordCraft images were generated offscreen with `egui_kittest`/WGPU on Windows from the validated merge source tree, while it was staged before the source commit was created. The source commit records that same tree; the evidence branch adds only this README, a manifest, PNGs and attribution. No Microsoft or other vendor UI was captured. Documents/templates are WordCraft's original synthetic fixtures.

Each state is 1100×750 pixels at 1 pixel per point and settles for 20 frames. `en` and the private, test-only `qaa-rtl-latin` fixture use identical English labels to isolate layout direction. The states are Home, Paste menu, Insert, Options, Navigation pane, Paragraph, Font, chart data, save prompt, Start screen and empty window.

The source passed all six `cargo xtask ci` stages locally; UI library: 581 passed, 0 failed, 2 ignored. Geometry regressions cover inline menu arrows, Font width, template caption/row height, custom icon anchors, recent paths and navigation. Additional tests cover contextual logical values, mixed choice clicks and document preservation. These captures are visual evidence at these dimensions, not exhaustive pixel equivalence or physical/browser testing. Earlier exact-main pixel comparisons belong to the older submission and were not repeated for this integration.

## Reproduce

From the source checkout in PowerShell:

```powershell
$env:WORDCRAFT_RTL_AUDIT_DIR = Join-Path $env:TEMP 'wordcraft-rtl-captures'
cargo test --workspace tests_rtl::local_direction_screenshots -- --exact --nocapture
```

The fixture is compiled only for tests. GPU support is required. [`captures.json`](captures.json) records the source tree and SHA-256 hashes. Every PNG is listed in the evidence branch's `ATTRIBUTION.md`. No capture is added to the code PR diff.
