## 2024-05-23 - Fast Directory Traversal for Python scripts
**Learning:** For repositories processing hundreds of files (e.g., markdown parsing scripts scanning 800+ skill directories), `os.scandir` is ~6x faster than `glob.glob('skills/*/')`. Unlike glob, it requires explicit error handling (`FileNotFoundError`) and explicit hidden file ignoring (`not f.name.startswith('.')`).
**Action:** Replace `glob.glob` with `os.scandir` on scripts traversing large numbers of repository files, provided proper edge cases (missing directory, hidden files) are handled.
