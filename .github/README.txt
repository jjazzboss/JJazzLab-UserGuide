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

