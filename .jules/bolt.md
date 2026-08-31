## 2024-05-19 - Regex Compilation Overhead in Python Scripts
**Learning:** Using `re.match` with an inline string pattern repeatedly inside a loop causes Python to continuously check its internal regex cache, introducing measurable overhead in the form of `__init__.py:match` invocations. Precompiling regex at the module level significantly reduces function call overhead.
**Action:** Always hoist and `re.compile()` regular expressions when they are used within loops or called frequently across multiple file evaluations.
