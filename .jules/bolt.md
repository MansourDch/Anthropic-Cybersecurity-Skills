
## 2026-10-16 - Directory Listing Optimization
**Learning:** `os.scandir` is significantly faster than `glob.glob` for large directory listings, but requires explicit `is_dir()` and `startswith('.')` checks to mimic `glob`'s implicit behavior.
**Action:** Use `os.scandir` instead of `glob` in scripts processing many files, making sure to handle `FileNotFoundError` and explicit filtering.
