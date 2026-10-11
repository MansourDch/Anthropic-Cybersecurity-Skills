## 2026-10-11 - Speeding up directory traversal in validation script
**Learning:** Using `glob.glob` to list directories recursively or with wildcards is slower than using `os.scandir`, which yields `DirEntry` objects with cached properties.
**Action:** When filtering files/directories based on names and types, use `os.scandir` instead of `glob.glob` in performance-sensitive scripts.
