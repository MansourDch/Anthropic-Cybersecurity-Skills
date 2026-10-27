
## 2026-10-27 - Optimizing Directory Enumeration
**Learning:** `glob.glob` is significantly slower than `os.scandir` for directory enumeration in Python, but `os.scandir` requires explicit handling for hidden files and `FileNotFoundError`.
**Action:** Use `os.scandir` with `f.is_dir()` and `not f.name.startswith('.')` for high-performance directory listing where `glob` wildcards aren't strictly necessary.
