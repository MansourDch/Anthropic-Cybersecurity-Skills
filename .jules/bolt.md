## 2026-10-23 - Directory Traversal Performance
**Learning:** `glob.glob` with wildcards (`*`) is surprisingly slow compared to `os.scandir` in Python when iterating over large directories because it performs many redundant `stat` and `join` calls internally.
**Action:** Prefer `os.scandir` with explicit `is_dir()` and string filtering over `glob.glob` for directory listing in performance-sensitive scripts, but remember to manually filter out hidden files (`not f.name.startswith('.')`) which `glob` handles implicitly.
