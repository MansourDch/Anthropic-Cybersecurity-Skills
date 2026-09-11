
## 2024-05-24 - os.scandir is much faster than glob
**Learning:** Using `glob.glob("skills/*/")` is significantly slower than using `os.scandir()` for directory iteration when there are many items. In tests, it was ~5x slower.
**Action:** Replace `glob.glob` with `os.scandir()` for directory discovery in CLI tooling to improve performance, especially when filtering by directory type.
