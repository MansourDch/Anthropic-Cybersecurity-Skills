## 2024-10-05 - Directory Listing Performance
**Learning:** Using `glob.glob("skills/*/")` is significantly slower than `os.scandir()` for large directory counts. `os.scandir()` is highly optimized because it doesn't build a full list of path strings initially or check glob patterns unnecessarily.
**Action:** When scanning directories in Python, use `os.scandir()` inside a `try/except FileNotFoundError` block, filtering manually (e.g., `not f.name.startswith('.')`) instead of relying on `glob`.
