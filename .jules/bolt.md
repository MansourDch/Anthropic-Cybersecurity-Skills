## 2024-05-18 - Precompile regexes inside Python scripts
**Learning:** High frequency inline `re.match(...)` checks using string literals in loops incur a noticeable compilation and cache overhead even when python caches regexes under the hood. In loops with many evaluations, pulling regex compilation out to a module-level `re.compile()` and calling `.match()` directly avoids overhead.
**Action:** When working on Python validators/parsers, especially loop-heavy text processing, define regexes at the module level using `re.compile()` and reuse them.
