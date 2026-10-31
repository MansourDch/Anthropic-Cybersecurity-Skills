
## 2026-10-31 - [Replacing glob with os.scandir]
**Learning:** Using `os.scandir` is over 3x faster than `glob` for flat directory iterations. However, `glob` ignores hidden files by default when using `*`, so explicitly adding `not f.name.startswith('.')` is required to maintain parity.
**Action:** Prefer `os.scandir` for performance-critical directory reading in Python, but always manually filter out hidden directories if replacing a `glob` wildcard.
