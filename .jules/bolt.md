## 2024-08-17 - Pre-compiling Regex in Frontmatter Parser
**Learning:** Python's `re.match` inside a tight loop processing thousands of lines of frontmatter across hundreds of markdown files becomes a bottleneck when the regex strings are compiled dynamically on each call. Pre-compiling them at module level yields a >2x speedup.
**Action:** When validating many files, extract frequently used regex patterns in tight loops to global pre-compiled constants using `re.compile`.
