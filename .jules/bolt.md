## 2026-10-09 - Faster Directory Listing with os.scandir
**Learning:** `glob.glob` can be surprisingly slow for simple directory listing due to internal stat calls and path matching overhead.
**Action:** Use `os.scandir()` instead for faster iteration, but explicitly handle hidden files (`not f.name.startswith('.')`) and missing directories (`FileNotFoundError`) to maintain parity with `glob`.
