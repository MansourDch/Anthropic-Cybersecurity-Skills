## 2024-08-09 - Pre-compiling Regex in Frontmatter Parser
**Learning:** The simple custom frontmatter parser in `tools/validate-skill.py` calls `re.match` heavily inside an implicit loop over every line in thousands of `SKILL.md` files. This implicit cache miss overhead from uncompiled strings makes it quite slow when scaling up.
**Action:** Always pre-compile frequently used `re` pattern strings to a module-level `re.Pattern` object when they will be run within heavy loops parsing numerous markdown files.
