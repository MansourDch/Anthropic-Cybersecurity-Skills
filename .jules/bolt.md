## 2026-11-11 - Faster directory listing with os.scandir
**Learning:** Using `glob.glob()` with wildcards for large directory structures is significantly slower because it has overhead parsing hidden files and resolving wildcards.
**Action:** Use `os.scandir()` for faster directory iteration when explicitly filtering on directories and hidden files.
