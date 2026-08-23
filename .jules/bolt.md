## 2026-08-23 - Pre-compile Regex in Python
**Learning:** Compiling regex patterns globally instead of locally inside a function can provide noticeable performance gains in python, especially when called repeatedly.
**Action:** Use pre-compiled regex objects for functions with high execution frequency.
