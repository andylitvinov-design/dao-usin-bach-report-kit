# Repo Agent Notes

## File Links That Open Reliably In Chat

Problem:
- Chat links can fail when a file path contains Cyrillic characters, spaces, or decomposed Unicode symbols.

Rule:
- For any file I want the user to open from chat, create a mirror copy in an ASCII-only path with no spaces.
- Preferred stable folder: `/Users/andriilitvinov/projects/alchemy_reports`.
- Preferred filename style: `snake_case` in ASCII, e.g. `case1_primary_template.md`.
- Share links only to this stable copy.

Process:
1. Save or generate the main file.
2. Copy it to the stable ASCII path.
3. Verify the file exists (`ls -l`) and is readable (`sed -n '1,20p'`).
4. Return the clickable absolute link to the stable copy.

Link format:
- `[name](/Users/andriilitvinov/projects/alchemy_reports/file_name.md)`
