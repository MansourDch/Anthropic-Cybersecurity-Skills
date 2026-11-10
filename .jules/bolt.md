## 2026-11-10 - Replace glob with os.scandir for directory listing
**Learning:** Python's `glob.glob("skills/*/")` is significantly slower than `os.scandir()` for flat directory listings, taking ~20ms vs ~1ms for the existing skill directories.
**Action:** When listing directories in performance-sensitive scripts, prefer `os.scandir()` with a context manager and manual filtering over `glob`. Note that `glob` ignores hidden files by default, so `not f.name.startswith('.')` must be explicitly added to `os.scandir` to maintain functional parity.
