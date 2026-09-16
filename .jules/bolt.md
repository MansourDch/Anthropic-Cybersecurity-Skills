## 2024-05-24 - Faster directory listing with os.scandir
**Learning:** For Python directory listing, `os.scandir()` with `f.is_dir()` is significantly faster than `glob.glob()`, avoiding unnecessary string allocations and stat calls.
**Action:** Use `os.scandir` wrapped in a `try/except FileNotFoundError` instead of `glob` for better performance on I/O bound scripts, especially in large codebases.
