---
wiki_root: /mnt/g/My Drive/RBK-OBSIDIAN-NOTES/rbk-obsidian-vault/Agent Access/rbk-pkm-wiki

blacklist: []

index_excludes:
  - raw/
  - archive/
  - ingested/

ingested_folder: ingested

ingested_subdirs:
  - clippings
  - documentation
  - articles
  - notes
  - data
  - assets

log_format: "## [YYYY-MM-DD] {type} | {subject}"
---

**wiki_root:** Absolute path to the rbk-pkm-wiki root — the folder containing raw/, ingested/, and rbk-main-wiki/.

**blacklist:** Skill definition folders — wiki page creation is forbidden here.

**index_excludes:** Paths excluded from index.md tracking.

**ingested_folder:** Folder where processed source files are archived (relative to wiki_root).

**ingested_subdirs:** Archival taxonomy within ingested_folder.

**log_format:** Do not change without updating all wiki skills.
