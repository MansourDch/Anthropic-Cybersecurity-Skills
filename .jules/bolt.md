## 2026-11-06 - Replace glob with os.scandir for directory listing
**Learning:** `glob.glob` is significantly slower than `os.scandir` for directory enumeration in Python, especially in large directory structures. Using `glob.glob` with trailing slashes like `*/` forces stat calls internally, while `os.scandir` retrieves type information directly from the directory entries.
**Action:** Prefer `os.scandir` with `f.is_dir()` over `glob.glob` when enumerating directories, and explicitly handle hidden files (`not f.name.startswith('.')`) to maintain functional parity.
