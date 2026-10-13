# RTL review evidence

Original WordCraft screenshots, MIT OR Apache-2.0; see ATTRIBUTION.md.
These files are published only on the fork's evidence branch, outside the code PR.
The parent commit of the evidence commit is the submitted code.

Tested source tree: `f7757d383a24d29e80d0f06adb1c626d5ea9cec1`.

The same English labels are used in LTR and RTL. There is no Arabic translation
in these images and no shipping catalog in the proposal. Document direction is
unchanged. Captures were allowed 20 frames to settle cached intrinsic sizes.
Font labels also have a separate 30-frame clip-bound regression.

```powershell
$env:WORDCRAFT_RTL_AUDIT_DIR = 'plan/rtl-captures'
cargo test --locked -p wordcraft-ui-egui --lib tests_rtl::local_direction_screenshots -- --exact --test-threads=1
```

- `en-home.png`: LTR Home.
- `qaa-rtl-latin-home.png`: RTL Home, identical labels and sample document.
- `qaa-rtl-latin-options.png`: RTL Options.
- `qaa-rtl-latin-dialog.png`: RTL Paragraph dialog.
- `qaa-rtl-latin-font.png`: RTL Font dialog, including choice controls in a grid.
- `qaa-rtl-latin-chart-data.png`: eight-series chart form at the initial scroll position.
  The last series at the far scroll edge is covered by the full-form geometry test.

`ltr-comparison.json` contains the raw comparison of 28 fresh LTR captures to
saved original-main captures: 18 identical, 9 caret-only, 1 greeting-only.
The strict comparator rejects the greeting difference; no exact 28/28 pixel pass
is claimed. `validation.json` identifies the source tree and the quality gate.
No Microsoft screenshot, asset, wording or document is included.
