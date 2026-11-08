
## 2026-11-08 - os.scandir vs glob.glob performance
**Learning:** `os.scandir` is significantly faster than `glob.glob` for directory listing as it avoids unnecessary stat calls and path manipulations, but it requires handling hidden files (`.startswith('.')`) and missing directories (`FileNotFoundError`) manually.
**Action:** When directory traversal is a bottleneck, use `os.scandir` with a context manager and explicit filtering instead of `glob.glob`, ensuring path separators remain consistent via f-strings rather than `os.path.join`.
