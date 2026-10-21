## 2026-10-21 - os.scandir is significantly faster than glob for directory listing
**Learning:** In Python scripts traversing many directories, `glob.glob` can be very slow compared to `os.scandir`. In `tools/validate-skill.py`, replacing `glob.glob("skills/*/")` with `os.scandir("skills")` reduced directory listing time significantly.
**Action:** Use `os.scandir` for directory listing on hot paths or large directory structures, but remember to handle `FileNotFoundError` and manually filter out hidden files (`not f.name.startswith('.')`) to maintain parity with `glob`.
