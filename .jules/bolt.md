## 2024-05-19 - Python re.match Implicit Cache Overhead

**Learning:** When using Python's `re.match` inside a tight loop (like parsing hundreds of YAML frontmatter blocks line-by-line), relying on Python's implicit regex caching (which `re.match` uses) still adds significant overhead compared to explicitly precompiling with `re.compile`. In a codebase with ~800+ skills to validate, inline `re.match` accounted for a disproportionate number of implicit `_compile` function calls (over 25,000 per run), slowing down the validation script.

**Action:** Always precompile regular expressions using `re.compile()` at the module level when they will be called repeatedly inside loops or applied across many lines/files, especially in validation scripts where speed is critical.
