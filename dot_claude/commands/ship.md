# Ship Changes

Commit all changes, push to remote, and open a Pull Request.

## Steps

1. **Review changes**: Run `git status` and `git diff` to understand what will be committed
2. **Stage changes**: Add all relevant files (exclude any that shouldn't be committed)
3. **Commit**: Create a well-formatted commit message that:
   - Summarizes the changes concisely
   - Explains the "why" not just the "what"
   - Follows conventional commit format if the repo uses it
4. **Push**: Push to the remote branch (create upstream if needed)
5. **Open PR**: Use `gh pr create` to open a Pull Request with:
   - Clear title describing the change
   - Summary section with bullet points
   - Test plan section describing how to verify the changes

If there are any issues at any step, stop and report them before proceeding.
