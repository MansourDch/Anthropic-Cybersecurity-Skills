
## 2026-10-25 - Replace glob.glob with os.scandir for directory listing
**Learning:** os.scandir() is significantly faster than glob.glob() for directory listing (~6x faster) because it reads directory entries directly, making it much more efficient when iterating over hundreds of directories. However, to maintain parity, you must explicitly check `f.is_dir()`, ignore hidden files (`not f.name.startswith('.')`), and handle `FileNotFoundError`.
**Action:** When needing to iterate over a large number of directories in Python, prefer os.scandir() over glob.glob() for better performance, while ensuring parity for hidden files and missing directories.
