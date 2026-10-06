## 2026-10-06 - Faster directory traversal with os.scandir
**Learning:** Using `glob.glob()` for large directory listing is significantly slower than `os.scandir()` because `os.scandir` provides cached directory entries directly from the OS. However, it requires explicit error handling (`FileNotFoundError`) and manual filtering of hidden files (e.g., `.startswith('.')`) that `glob` handles by default.
**Action:** Default to `os.scandir()` instead of `glob` on hot paths for directory iteration, ensuring proper try/except and hidden file filtering to maintain functional parity.
