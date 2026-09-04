## 2024-05-24 - Profiling validate-skill.py

**Learning:** The `parse_frontmatter` function in `tools/validate-skill.py` is called for every `SKILL.md` file (over 800 times). It uses multiple `re.match` calls per line, which is a major bottleneck taking ~25% of the total script runtime.
**Action:** Replace regular expressions with equivalent string operations (e.g. `.partition(':')`, string slicing, `.startswith()`, and character checks) in high-frequency parsing paths to speed up execution. This reduces parsing time by almost 50% without altering output.
