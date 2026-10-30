## 2026-10-30 - Replace glob with os.scandir
**Learning:** `os.scandir` is significantly faster than `glob.glob` for gathering subdirectories, but requires careful handling of hidden files and missing directories.
**Action:** Use `os.scandir` instead of `glob` for performance-critical path traversal.
