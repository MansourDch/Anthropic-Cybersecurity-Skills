## 2024-10-01 - Directory Iteration Performance
**Learning:** Using `glob.glob` with a pattern like `*/*/` is significantly slower than using `os.scandir` when fetching a large number of directories, because `glob` performs multiple `stat` calls and path concatenations internally.
**Action:** Use `os.scandir` for faster directory enumeration, especially on hot paths or large directories. Remember to manually filter out hidden directories (starting with `.`) and handle `FileNotFoundError`.
