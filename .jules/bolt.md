
## 2026-10-10 - os.scandir vs glob.glob for directory listing
**Learning:** `glob.glob` is significantly slower than `os.scandir` for shallow directory listing because it performs extra internal filtering and stat calls. However, when switching to `os.scandir`, we must explicitly handle `FileNotFoundError` (which `glob` ignores) and manually exclude hidden files/directories (which `glob` ignores automatically) to maintain functional parity.
**Action:** Use `os.scandir` with explicit `f.is_dir()` and hidden file exclusion logic for performance-critical directory listing instead of `glob.glob`.
