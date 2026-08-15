## 2024-06-25 - Python File Reading Optimization Trap
**Learning:** In script optimizations, truncating file reads (e.g. only reading YAML frontmatter and not the markdown body) based purely on perceived necessity can introduce regressions if downstream functions silently depend on the full file content.
**Action:** Always verify if all data read from a file is strictly unused before truncating the read operation, especially in validation scripts where unexpected checks may occur later.
