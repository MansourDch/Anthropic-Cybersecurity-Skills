## 2026-10-04 - Optimize directory traversal with os.scandir
**Learning:** Using `glob.glob("skills/*/")` is significantly slower than using `os.scandir()` for directory listing, as `glob` performs extra stat calls and string matching overhead. In python, `os.scandir()` provides a highly optimized iterator for directory contents.
**Action:** Use `os.scandir()` with explicit filtering (`f.is_dir() and not f.name.startswith('.')`) instead of `glob.glob()` on hot paths or when enumerating large directories to improve startup and traversal times.
