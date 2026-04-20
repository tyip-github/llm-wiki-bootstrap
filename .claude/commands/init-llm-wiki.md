Create a new LLM Wiki by copying the base template and configuring it for the user.

## Steps

1. Ask the user: "What is the topic of this wiki?" Wait for their response.

2. Ask the user: "What should the Obsidian vault be named?" (This becomes the root directory name.) Wait for their response.

3. Ask the user: "Where should the vault be saved? (Provide the parent folder path, e.g. ~/Documents)" Wait for their response.

4. Copy the entire contents of `templates/base/` to `<folderpath>/<vault-name>/`:
   ```
   cp -r templates/base/ <folderpath>/<vault-name>/
   ```

5. In the new `<folderpath>/<vault-name>/CLAUDE.md`, replace `[YOUR TOPIC HERE]` with the topic the user provided.

6. Report what was created:
   - The vault path
   - The folder structure
   - Tell the user to open Obsidian and use "Open folder as vault" to select `<folderpath>/<vault-name>/`
