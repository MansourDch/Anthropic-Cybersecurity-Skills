## 2026-08-18 - Avoid re.match inside loops
**Learning:** `re.match` inside a loop for frequently called functions creates overhead due to Python checking its regex cache and wrapping function calls. Even with the internal cache, calling `re.compile().match()` directly is measurably faster.
**Action:** Always pre-compile regexes at the module level when they are used inside tight loops or frequently called parsers.
