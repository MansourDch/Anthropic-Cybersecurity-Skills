## 2024-05-28 - Replacing glob.glob with os.scandir for faster directory listing
**Learning:** `glob.glob` is significantly slower than `os.scandir` for directory listings on repositories with many directories because it performs more filesystem operations.
**Action:** Always prefer `os.scandir` over `glob.glob` for shallow directory traversal in Python scripts for faster execution, wrapping it in a `try/except FileNotFoundError` for safety.
