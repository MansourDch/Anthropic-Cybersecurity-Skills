
## 2024-09-13 - scandir FileNotFoundError
**Learning:** Unlike `glob.glob`, `os.scandir` raises a `FileNotFoundError` if the target directory doesn't exist, which can break graceful error handling logic relying on empty list returns.
**Action:** Always wrap `os.scandir` in a `try/except FileNotFoundError` when replacing `glob` if the original code gracefully checked for an empty list.
