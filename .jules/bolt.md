## 2026-09-01 - O(N^2) YAML List Copying
**Learning:** In `tools/validate-skill.py`'s custom frontmatter parser, copying `list_values` on every single iteration of a list (`data[current_key] = list(list_values)`) results in O(N^2) complexity for large lists. For small lists (e.g. 10 items) it's still overhead but relatively minor.
**Action:** When manually parsing arrays/lists, avoid creating a new copy on every appended item. Simply mutate the list in-place and assign a reference to the dict, or set the reference on the first item and mutate in place thereafter.
