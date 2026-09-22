## 2024-05-24 - Directory Iteration Performance
**Learning:** Using `os.scandir` is significantly faster than `glob.glob` because it returns cached properties directly from the OS, eliminating the need for extra stat calls and path parsing. However, it requires a try/except block for missing directories and explicit filtering for hidden files (`not f.name.startswith('.')`).
**Action:** Default to `os.scandir()` instead of `glob` or `os.listdir` in Python for hot-path file system traversals to maximize iteration speed.
