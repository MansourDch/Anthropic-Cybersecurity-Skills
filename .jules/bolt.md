## 2026-08-22 - Python Regex Pre-compilation in Parsers
**Learning:** Python caches recently used regexes, but explicit compilation with `re.compile()` still saves overhead (cache dictionary lookup) in tight loops like line-by-line file parsing.
**Action:** Always prefer module-level pre-compiled regex objects for scripts that process large numbers of files or lines.
