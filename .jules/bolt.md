## 2026-10-15 - Optimizing directory listing with os.scandir
**Learning:** Using `os.scandir()` with explicit checks (`entry.is_dir()` and avoiding hidden files) is significantly faster than `glob.glob("skills/*/")` for listing directories. However, it requires a `try/except FileNotFoundError` block because `os.scandir` fails if the directory doesn't exist, unlike `glob`.
**Action:** Default to `os.scandir()` instead of `glob.glob()` for directory traversal when performance is critical, ensuring proper error handling and explicit filtering of hidden files are implemented.
