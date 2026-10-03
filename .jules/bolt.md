## 2026-10-03 - Avoid over-optimizing glob
**Learning:** `glob.glob` seems to be slow in some contexts, but `os.scandir` is faster for directory listing.
**Action:** Replace `glob.glob` with `os.scandir` for directory listing to optimize validation, explicitly adding `not f.name.startswith('.')` to maintain functional parity.
