## 2026-10-18 - os.scandir is much faster than glob.glob
**Learning:** For listing files/directories, `os.scandir` is significantly faster than `glob.glob`, providing an almost 10x speedup in directory traversal.
**Action:** Replace `glob.glob("skills/*/")` with `os.scandir("skills")`. Note that `glob` ignores hidden directories (starting with `.`), so `os.scandir` must also explicitly filter out names starting with `.` to match behavior.
