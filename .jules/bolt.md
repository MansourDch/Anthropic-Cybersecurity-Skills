## 2026-11-04 - [Performance] Optimize directory listing in validate-skill.py
**Learning:** Using `glob.glob("skills/*/")` is significantly slower than `os.scandir("skills")` with `f.is_dir()` checks when listing hundreds or thousands of skill directories, due to the overhead of path parsing and checking in `glob`.
**Action:** Use `os.scandir()` instead of `glob` for performance-critical directory listing operations, remembering to add `not f.name.startswith('.')` to filter out hidden directories which `glob` ignores by default.
