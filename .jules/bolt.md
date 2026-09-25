
## 2026-09-25 - Replace glob with os.scandir for directory listing
**Learning:** In Python, `os.scandir()` with `.is_dir()` checks is significantly faster than `glob.glob()` for listing directories. However, to maintain functional parity with `glob`, `os.scandir` requires explicitly filtering out hidden files (`not f.name.startswith('.')`) and handling `FileNotFoundError` if the directory is missing.
**Action:** Use `os.scandir()` instead of `glob` for large directory traversal when performance matters, but remember to explicitly handle hidden files and missing directories to prevent crashes or behavioral changes.
