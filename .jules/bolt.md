## 2026-10-29 - Optimize directory listing with os.scandir
**Learning:** `glob.glob("skills/*/")` is significantly slower than `os.scandir("skills")` because `glob` performs multiple stat calls and pattern resolution, whereas `os.scandir` yields directory entries with cached file types, yielding massive speedups for flat directory scans.
**Action:** Use `os.scandir()` with `f.is_dir()` and explicit dotfile filtering (`not f.name.startswith('.')`) instead of `glob` when listing flat directories for performance.
