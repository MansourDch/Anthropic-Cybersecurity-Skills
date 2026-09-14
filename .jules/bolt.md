
## 2026-09-14 - Directory Traversal Bottleneck in validation scripts
**Learning:** In Python, `glob.glob("skills/*/")` is significantly slower (up to 7x) than `os.scandir("skills")` with `f.is_dir()` for directory listing due to `glob` stat'ing multiple paths internally and not exposing object types efficiently.
**Action:** Replace `glob.glob()` with `os.scandir()` wrapped in a `try/except FileNotFoundError` block in CLI tools handling large repositories for faster cold starts.
