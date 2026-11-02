## 2026-11-02 - Optimize validate-skill.py
**Learning:** `glob.glob` is significantly slower than `os.scandir` when parsing many directories.
**Action:** Always prefer `os.scandir` for directory traversal in Python.
