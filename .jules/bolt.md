## 2024-05-15 - Optimizing directory traversal in Python scripts
**Learning:** `glob.glob` with wildcard matching is significantly slower than `os.scandir()` for finding directories, especially when run in large repositories or loops.
**Action:** Use `os.scandir()` with `is_dir()` checks instead of `glob.glob("*/")` for faster directory traversal, while ensuring `FileNotFoundError` handling and filtering out hidden files (`not f.name.startswith('.')`) to maintain functional parity.
