## 2026-08-26 - Pre-compiling Regex in validate-skill.py
**Learning:** Bypassing `re.match` with precompiled module-level regex variables reduces function call overhead in tight loops even though Python caches regular expressions implicitly. Profiling showed 78k fewer primitive function calls.
**Action:** Always precompile static regular expressions in tight loops across large file trees.
