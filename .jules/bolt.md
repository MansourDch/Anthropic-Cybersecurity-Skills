## 2024-10-02 - Directory Listing Performance
**Learning:** Using `glob.glob` with wildcards is significantly slower than `os.scandir` for directory listing because `glob` performs more stat calls and doesn't utilize the pre-cached attributes from the OS directory iterator.
**Action:** Prefer `os.scandir()` with `is_dir()` checks and explicit hidden file filtering (`not f.name.startswith('.')`) for high-performance directory traversal. Remember to handle `FileNotFoundError` which `scandir` raises if the directory is missing.
