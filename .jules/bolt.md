## 2025-02-28 - Regex pre-compilation inside frontmatter parsing loop
**Learning:** In highly repetitive text parsing operations, like iterating over lines of hundreds of YAML files to find matching key-value pairs, using `re.match(r"...", text)` dynamically results in significant repeated compilation overhead.
**Action:** Always extract static regular expressions out of loops or hot paths and use `re.compile()` at the module level.
