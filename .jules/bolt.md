
## 2024-05-18 - Replacing glob.glob with os.scandir for directory discovery
**Learning:** When listing subdirectories, `glob.glob("skills/*/")` is significantly slower than `os.scandir("skills")` in Python, especially for large numbers of items, because `os.scandir` avoids unnecessary stat calls. However, unlike `glob`, `os.scandir` raises `FileNotFoundError` if the root directory is missing.
**Action:** Always prefer `os.scandir` over `glob` for performance when discovering files/directories, but ensure it is wrapped in a `try/except FileNotFoundError` block to preserve graceful fallbacks when the target directory does not exist.
