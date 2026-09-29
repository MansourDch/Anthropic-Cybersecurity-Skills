## 2026-09-29 - os.scandir vs glob.glob performance
**Learning:** Using `os.scandir()` with `f.is_dir()` checks is significantly faster (~3x) than `glob.glob("*/")` for listing directories, but requires explicit handling for hidden directories (which `glob` ignores by default) and raises `FileNotFoundError` if the root directory is missing.
**Action:** When replacing `glob` with `os.scandir` for performance, always include `not f.name.startswith('.')` to maintain functional parity and wrap in a `try/except FileNotFoundError` block.
