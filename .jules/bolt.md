## 2023-10-27 - Python regex cache lookup overhead in tight loops
**Learning:** Even though Python caches compiled regular expressions internally when using `re.match(pattern, string)`, the dictionary lookup overhead in this cache becomes a measurable bottleneck in tight parsing loops (like parsing frontmatter across 800+ SKILL.md files).
**Action:** Always pre-compile regular expressions (`re.compile`) at the module level when they are used inside tight iteration loops over many files.
