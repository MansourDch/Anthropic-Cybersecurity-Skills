## 2026-10-26 - Directory listing bottleneck in validation script
**Learning:** In Python validation scripts operating on large directories, `glob.glob` is significantly slower than `os.scandir`. `os.scandir` avoids excessive `stat` system calls by fetching directory entries and attributes simultaneously.
**Action:** Default to `os.scandir` over `glob` for hot-path directory traversals in Python scripts, ensuring to handle `FileNotFoundError` and explicitly filter out hidden files (`startswith('.')`) to maintain functional parity.
