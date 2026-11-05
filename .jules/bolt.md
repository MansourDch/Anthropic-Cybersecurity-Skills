## 2026-11-05 - os.scandir vs glob for large directories
**Learning:** `os.scandir()` is significantly faster than `glob.glob()` for listing directories when there are many folders. However, it requires manually filtering hidden files (e.g., `not f.name.startswith('.')`) and handling `FileNotFoundError` to match `glob`'s behavior and avoid crashes.
**Action:** Use `os.scandir` instead of `glob` on hot paths involving large directory listings, ensuring proper filtering and exception handling are implemented.
