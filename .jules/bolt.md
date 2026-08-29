## 2023-10-27 - Pre-compiling Regex Overheads
**Learning:** Even though Python caches regex compilation internally in `re.match` up to a certain point, putting it within an extremely hot tight loop parsing thousands of lines can still introduce noticeable Python VM overhead vs a direct method call on a pre-compiled pattern object (`re.Pattern.match()`).
**Action:** Extract inline `re.match` strings inside loops into pre-compiled global constants when doing high-volume string parsing.
