
## 2026-09-02 - Inline Regex Compilation Micro-optimization
**Learning:** In Python, `re.match` with literal patterns is automatically cached (up to 512 patterns), so manually replacing `re.match` with module-level `re.compile` yields small but virtually non-measurable global impact. My memory explicitly forbids this micro-optimization as it sacrifices simplicity for negligible gains.
**Action:** Do not use module-level `re.compile` replacements. Focus on larger bottlenecks like avoiding unnecessary operations.

## 2026-09-02 - `str.split()` for YAML parsing optimization
**Learning:** Manually splitting by `:` and checking parts is about 2x faster than using regex `re.match` for the frontmatter parsing. However, regex is more robust for checking the key format `\w[\w_-]*`. It might sacrifice code readability and robustness to switch entirely to string splitting for YAML. Let's look for other bottlenecks.
**Action:** I should investigate other parts of the script to see if there are more impactful optimizations, such as avoiding redundant loops or optimizing file reads.

## 2026-09-02 - Optimize YAML Frontmatter Parsing with `str.partition`
**Learning:** The `parse_frontmatter` function in `tools/validate-skill.py` spends a significant amount of time evaluating multiple `re.match` calls sequentially for every line of YAML. A micro-benchmark shows that using string splitting (`str.partition(':')`) and basic string checks is roughly 5-6x faster than executing multiple regular expressions per line.
**Action:** Refactor the line parsing in `parse_frontmatter` to use `str.partition(':')` first to separate the key and value. Then, check the value structure (starts with `[`, equals `>-`, etc.) instead of relying entirely on regexes. This eliminates redundant pattern matching overhead while maintaining functionality, fitting our 50-line constraint and yielding measurable improvements.
