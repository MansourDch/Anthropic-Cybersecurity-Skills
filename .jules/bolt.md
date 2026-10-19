## 2026-10-19 - Fast Directory Listing
**Learning:** `os.scandir()` is significantly faster than `glob.glob()` for listing directories because it retrieves file attributes (like is_dir()) from the directory stream directly, avoiding extra system calls. However, unlike glob, it doesn't automatically ignore hidden files (starting with '.') and can raise FileNotFoundError if the directory is missing.
**Action:** Always prefer `os.scandir()` over `glob.glob()` for directory listings where performance matters, but remember to manually filter out hidden files and handle FileNotFoundError.
