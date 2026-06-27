# generate-catalog-efu

## Purpose
This skill generates a file catalog of the entire repository in the Everything (EFU) format, saved as a CSV file to be viewable in the AI Studio editor.

## When to use
Use this skill when the user asks to generate a catalog, file list, or EFU file of the repository.

## Inputs and assumptions
- The script uses Node.js.
- An npm script `generate-efu` is defined in `package.json`.
- The target file is generated as `catalog.efu.csv` at the repository root.

## Procedure
To execute this skill, run the following command at the root of the repository:
```bash
npm run generate-efu
```
This will execute `node scripts/generate-efu.js`.

## Safety rules
- Do not expose any local absolute paths that might leak machine information. The script already converts absolute paths to repository-relative paths.
- Do not run any destructive file modifications as part of this skill.

## Verification
- Confirm that `catalog.efu.csv` was created at the repository root.
- Ensure that the file does not contain `.git` or `node_modules` paths by inspecting its contents using a file view tool.

## Related files
- `scripts/generate-efu.js`
- `package.json`
- `catalog.efu.csv`
