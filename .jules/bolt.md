## 2026-11-07 - Optimize directory scanning with os.scandir
**Learning:** Using `glob.glob()` with wildcards for directory scanning is significantly slower than `os.scandir()` because `os.scandir` yields `DirEntry` objects that cache file attributes, preventing extra stat calls, and it avoids fully materializing lists in memory.
**Action:** When scanning directories iteratively, particularly for filtering by attributes (like `.is_dir()`), use `os.scandir()` instead of `glob.glob()`. Also, manually filter hidden files (`not f.name.startswith('.')`) to maintain functional parity with `glob`.
