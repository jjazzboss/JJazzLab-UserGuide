 Added a manual Copilot-driven translation workflow at .github/workflows/manual-translation-sync.yml and the shared prompt at
  .github/copilot/translate-docs-prompt.txt.

  It works like this:

   - run it manually from GitHub Actions
   - provide from_ref and optionally to_ref, languages, dry_run
   - for each selected language branch, it creates/updates ai-sync/<language>/<sha>
   - uses Copilot CLI to update only changed Markdown pages
   - runs the repo’s Lychee link check
   - opens or updates a PR targeting french, spanish, japanese, or german

  I also updated .github/copilot-instructions.md so future sessions know this workflow exists and where the translation rules
  live.

  Before using it, add a repository secret named COPILOT_PAT containing a fine-grained PAT with Copilot Requests permission.
  Then you can trigger the workflow manually from the GitHub Actions tab.

	Copilot CLI runs on the GitHub Actions runner, not on your computer.

  So when you start the workflow from the Actions tab:

   - GitHub provisions a runner VM/container
   - the workflow checks out the repo there
   - installs @github/copilot there
   - runs the Copilot prompt there
   - creates branches/PRs from there

  Your computer is only used to trigger the workflow and later review/merge the PRs. The only credential you provide is the 
  COPILOT_PAT secret stored in the repository or organization settings, which the runner uses during the job.


Added bootstrap support to .github/workflows/manual-translation-sync.yml.

What changed

 - New full_sync input: when true, the workflow translates all published .md files from to_ref, not just diffs.
 - In bootstrap mode, the PR branch is created from origin/master and opened against the target language branch.
 - Bootstrap PRs are named like Bootstrap french from master and use branches like ai-bootstrap/<language>/<sha>.
 - from_ref is now optional and ignored during bootstrap runs.

How to use it

 - Normal incremental sync: leave full_sync unchecked, set from_ref and optionally to_ref.
 - One-time reset/bootstrap: set:
  - full_sync = true
  - to_ref = origin/master
  - languages = french,spanish,japanese,german or a subset

That will generate one full translation PR per language branch from current English.
