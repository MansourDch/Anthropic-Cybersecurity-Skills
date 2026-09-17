## 2026-09-17 - os.scandir vs glob.glob performance
**Learning:** Using `glob.glob` to filter directories in `tools/validate-skill.py` (e.g. `glob.glob("skills/*/")`) is surprisingly slow compared to `os.scandir()`. Profiling showed `glob.glob()` taking significantly longer for listing 800+ skill directories.
**Action:** Replace `glob.glob()` with `os.scandir()` and explicit `f.is_dir()` checks on hot paths for directory iteration, ensuring to catch `FileNotFoundError` since `scandir` doesn't fail silently on missing directories like `glob` does.
