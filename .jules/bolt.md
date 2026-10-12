
## 2026-10-12 - Replacing glob with os.scandir for directory listing
**Learning:** In Python, `glob.glob` with wildcards can be surprisingly slow for large directories compared to `os.scandir`. `os.scandir` avoids unnecessary system calls and is often ~3x faster for iterating top-level directories. However, `os.scandir` requires manual filtering of hidden files and explicit `FileNotFoundError` handling to match `glob`'s behavior.
**Action:** Always prefer `os.scandir` over `glob` for shallow directory listing when performance is critical, but remember to manually filter out hidden files (`not f.name.startswith(".")`) and handle `FileNotFoundError`.
