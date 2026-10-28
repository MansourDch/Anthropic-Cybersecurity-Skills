## 2026-10-28 - Faster Directory Traversal with os.scandir
**Learning:** `glob.glob` with wildcards scales poorly and has higher overhead for directory filtering compared to `os.scandir()`. `os.scandir()` avoids unnecessary stat calls and string manipulations.
**Action:** Use `os.scandir()` instead of `glob.glob` for directory listings on hot paths or large directories, ensuring explicit handling of hidden files (`not f.name.startswith('.')`) and `FileNotFoundError`.
