# breakage.md

Known future risks: what could break, what would trigger it, what to check.

## CodeRabbit security review (.coderabbit.yaml), added 2026-11-03

- **Security review quietly stops.** Risk: CodeRabbit renames or drops a setting, the CodeRabbit app loses access to this repo, or someone changes this repo's settings in the CodeRabbit dashboard. Trigger: a pull request that gets no CodeRabbit walkthrough comment, or a CodeRabbit comment saying the config has errors. Check: the latest pull request has a CodeRabbit comment; validate the file with `uvx check-jsonschema --schemafile https://coderabbit.ai/integrations/schema.v2.json .coderabbit.yaml`.
- **Work pushed straight to the default branch is never reviewed.** CodeRabbit only reviews pull requests. Trigger: agents or people committing directly to the default branch. Check: the weekly Deep Scan in the CodeRabbit dashboard, which reads the whole repo.
