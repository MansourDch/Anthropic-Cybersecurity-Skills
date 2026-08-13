## 2024-05-13 - Regex Compilation
**Learning:** Python's `re.match` compiles the pattern on the fly and caches a small number of patterns, but explicitly pre-compiling regexes in tight loops (like parsing frontmatter across hundreds of files) guarantees faster execution.
**Action:** Pre-compile regexes at the module level when they are used in tight loops or large numbers of files.
