## 2024-05-24 - [Python Directory Listing Bottleneck]
**Learning:** Using `glob.glob("skills/*/")` is significantly slower (roughly 10x) than `os.scandir` when simply listing directories in a flat folder.
**Action:** Prefer `os.scandir("dir")` with `f.is_dir()` checks over `glob.glob` when listing immediate child directories in Python scripts for measurable speedups.
