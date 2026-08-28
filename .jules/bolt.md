## 2024-05-22 - Pre-compiling Regexes in YAML parsing
**Learning:** Repetitive regex matching inside a loop traversing line-by-line of YAML files can cause an overhead due to repeated regex compilation or cache checks.
**Action:** Always pre-compile `re.compile()` rules outside of the tight loops or function logic to module-level constants.
