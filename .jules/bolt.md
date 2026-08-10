## 2024-05-09 - Pre-compile Regexes in Scripts
**Learning:** Python's `re.match()` internal caching still has overhead compared to explicitly pre-compiling regexes with `re.compile()`. Over 100,000+ line executions, pre-compiling reduced script time from ~1.13s to ~0.45s.
**Action:** When working with scripts that parse many files iteratively, explicitly define and use compiled regexes at the module level instead of relying on `re`'s inline caching.
