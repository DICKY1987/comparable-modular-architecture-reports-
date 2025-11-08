TASK 0 — Insert “Current System README.md” as the first section of the report

GOAL
Create the first section, very top of the report, literally titled:

# Current System README.md

This section must contain the repository’s README content (or a generated README if none exists). Do NOT print any filesystem path in the report output.

INPUTS (fill if available)
- REPO_URL: {{REPO}}
- BASE_BRANCH: {{main}}

INSTRUCTIONS
1) Discover README
   - Look for an existing top-level README in this order: README.md, readme.md, README, README.rst.
   - If the file is .rst or plain text, convert to Markdown faithfully (preserve code blocks/tables).

2) If README exists
   - Render its contents directly under the heading “# Current System README.md”.
   - To avoid clashing H1s inside the report, DEMOTE internal README headings by one level (so the highest becomes “##”).
   - Preserve all prose, lists, tables, links, and fenced code blocks verbatim.
   - Do NOT include any file path or “Found at …” lines in the report.

3) If README is missing
   - Generate a minimal, accurate README under the same heading. Fill details from repository facts (package manifests, setup/config files, scripts, CI, docs).
   - If a datum cannot be proven, mark it as “TODO: <short note>” rather than guessing.
   - Use this skeleton (edit/expand based on repo evidence):


STANDARD SECTION ORDER (use as checklist)

1. Title + one-line value proposition
2. Badges (CI, coverage, release, license)
3. Overview (what it is / who it’s for)
4. Features (bulleted)
5. Usage (CLI/API examples)
6. Configuration (env vars, config files)
7. Architecture (short text + link to docs/ or diagram)
8. Development (repo layout, scripts, tests)
9. CI/CD (how it runs; how to release)

   ---

