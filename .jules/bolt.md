## 2026-09-26 - Python Directory Listing Optimization
**Learning:** In Python scripts, using `os.scandir` combined with `.is_dir()` and string checks is significantly faster (approx. 9x) than using `glob.glob("*/")` when iterating over a large number of directories, though it requires explicit handling for hidden files (`not f.name.startswith('.')`) to maintain parity.
**Action:** Default to using `os.scandir` instead of `glob.glob` for directory discovery on hot paths or large directory structures when optimizing Python scripts.
