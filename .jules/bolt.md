## 2024-09-19 - os.scandir() vs glob.glob()
**Learning:** Using os.scandir() with f.is_dir() checks is significantly faster than glob.glob() for directory listings in Python, avoiding unnecessary system calls. However, unlike glob, os.scandir raises a FileNotFoundError if the directory is missing, so it must be wrapped in a try/except block to preserve graceful fallback logic.
**Action:** Default to using os.scandir() instead of glob.glob() for performance-critical directory listing tasks, ensuring to handle potential FileNotFoundError exceptions.
