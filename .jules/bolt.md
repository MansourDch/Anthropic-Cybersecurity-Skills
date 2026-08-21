## 2024-06-25 - Python Regex Compilation in Loops
**Learning:** In heavily used loops (like parsing frontmatter across hundreds of markdown files), compiling regexes `re.compile()` at module level instead of calling `re.match(r"...")` on the fly yields measurable micro-performance improvements in Python, even though Python internally caches recent regex patterns.
**Action:** Next time looking for small optimisations in Python scripts, scan for `re.match` or `re.search` inside large loops and lift them to module-level constants.
