## 2026-11-03 - Replaced glob.glob with os.scandir
**Learning:** In Python, `os.scandir` is significantly faster than `glob.glob` for directory listings because it avoids stat calls and internal regex matching, but requires manual handling of hidden files and missing directories.
**Action:** When scanning large directories, prefer `os.scandir()` with `f.is_dir()` and `not f.name.startswith('.')` to avoid crashing on hidden files and missing directories.
