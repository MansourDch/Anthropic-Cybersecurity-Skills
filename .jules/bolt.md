## 2024-05-18 - Replacing `re.match` with string partitioning for YAML frontmatter parsing
**Learning:** `tools/validate-skill.py` calls `re.match` three times per line for every line of YAML frontmatter across ~800 files. Given the simple syntax, string operations (`partition`, `startswith`, `endswith`) are almost twice as fast as using the regex engine. Since this script runs on every PR, optimizing it saves time.
**Action:** Replace sequential `re.match` checks with a single string partition step, followed by fast manual validation and checking logic for lists, folded strings, and scalars.
