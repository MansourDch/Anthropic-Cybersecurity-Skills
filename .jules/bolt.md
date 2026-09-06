
## 2026-09-06 - Replacing regex with string manipulation in parse_frontmatter
**Learning:** Parsing 800+ YAML frontmatters by calling `re.match` line-by-line is relatively slow. Replacing simple regexes with `.partition(":")` and `.startswith()` checks avoids regex overhead and creates a measurable speedup. In our case, execution time dropped from 0.35s to 0.31s (~10% total execution speedup), and the parsing bottleneck time was cut almost in half.
**Action:** When parsing simple, predictably structured text formats (like specific YAML lines), prioritize native string operations over regex matching for small performance wins, while ensuring complete functional parity and strict validation preservation.
