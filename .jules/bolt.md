## 2023-10-24 - Speeding up directory traversal in python
**Learning:** Using `os.scandir()` with `f.is_dir()` and string condition checks is significantly faster than `glob.glob()`. However, we must explicitly ignore hidden files (`not f.name.startswith('.')`) to maintain functional parity with `glob` and handle `FileNotFoundError` gracefully.
**Action:** Default to `os.scandir()` instead of `glob.glob()` when scanning large directories where performance matters, being mindful of explicit hidden file exclusions and missing directory exceptions.
