## 2024-09-24 - Faster directory listing with os.scandir
**Learning:** For directory listing in Python scripts, using `os.scandir()` with `f.is_dir()` checks is significantly faster than `glob.glob()`. However, `os.scandir` raises `FileNotFoundError` if the directory is missing, and doesn't automatically ignore hidden files like `glob` does, so explicit handling is required.
**Action:** Use `os.scandir` for performance-critical directory traversal where appropriate, but ensure to explicitly check for missing directories and filter hidden files to maintain functional parity.
