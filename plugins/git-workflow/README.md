# Git Workflow Plugin

Smart git workflow orchestrator with intelligent intent recognition for commits, pushes, rebases, and PR management.

## Description

The Git Workflow plugin provides a comprehensive set of tools and agents to streamline your git operations. It analyzes your current git state, understands your intent, and executes the appropriate workflow automatically.

## Dependencies

**Required:**
- [GitHub CLI (`gh`)](https://cli.github.com/) - Used for PR operations
  ```bash
  # macOS
  brew install gh

  # Other platforms: https://github.com/cli/cli#installation
  ```

**Authentication:**
```bash
gh auth login
```

## Installation

```bash
/plugin install git-workflow
```

## Commands

### `/git-workflow`
Smart orchestrator that analyzes your current git state and executes the appropriate workflow based on context.

**Use cases:**
- Feature complete → Review → Commit → Push → PR
- Quick commit → Commit → Offer push/PR
- Rebase → Handle conflicts if needed → Offer force push
- Create PR → Validate → Generate content → Create

### `/git-commit`
Analyze changes and create atomic, searchable commits with conventional commit messages.

**Features:**
- Analyzes staged and unstaged changes
- Groups related changes into atomic commits
- Generates conventional commit messages
- Follows repository commit style

### `/git-branch`
Create a new branch with smart naming conventions and type inference.

**Branch naming pattern:**
```
<type>/<description-in-kebab-case>
```

**Types:**
- `feature/` - New features or enhancements
- `fix/` or `bugfix/` - Bug fixes
- `hotfix/` - Critical production fixes
- `refactor/` - Code refactoring
- `docs/` - Documentation updates
- `test/` - Test additions or updates
- `chore/` - Maintenance tasks

**Example:**
```bash
/git-branch add user authentication
# Creates: feature/add-user-authentication
```

### `/git-push`
Complete push workflow: commit → push → create/update PR.

**Workflow:**
1. Validates state (not on main)
2. Creates commits if there are uncommitted changes
3. Checks if branch is behind target
4. Pushes to remote (with `-u` for new branches)
5. Automatically creates or updates PR
6. Shows final summary

### `/git-pr`
Create or update a pull request for the current branch.

**Features:**
- Generates comprehensive PR description from commits
- Includes test plan
- Detects whether to create new or update existing PR
- Links to PR after creation

### `/git-rebase`
Rebase current branch onto target branch.

**Workflow:**
1. Validates state and fetches target
2. Starts rebase
3. If conflicts → delegates to git-conflict-resolver
4. After success, offers force push

**Usage:**
```bash
/git-rebase              # Rebases onto main (default)
/git-rebase develop      # Rebases onto develop
```

## Specialist Agents

The plugin uses specialized agents for different workflows:

### git-workflow-coordinator
Smart orchestrator that analyzes current git state and routes to appropriate specialists.

### git-commit-specialist
Creates atomic commits with conventional commit messages. Analyzes changes, groups related modifications, and generates meaningful commit messages following best practices.

### git-pr-specialist
Manages pull request creation and updates. Automatically detects whether to create a new PR or update an existing one. Generates comprehensive PR descriptions from commit history.

### git-conflict-resolver
Handles merge conflicts during rebase operations. Provides clear guidance and assistance for resolving conflicts.


## Usage Examples

### Complete workflow (feature ready to ship)
```bash
/git-push
```
This will:
- Commit any uncommitted changes
- Push to remote
- Create/update PR automatically

### Just commit changes
```bash
/git-commit
```

### Create a new feature branch
```bash
/git-branch implement oauth login
# Creates: feature/implement-oauth-login
```

### Fix a bug on a new branch
```bash
/git-branch fix broken validation
# Creates: fix/broken-validation
```

### Sync with main
```bash
/git-rebase main
```

### Let the coordinator decide
```bash
/git-workflow
```
The coordinator will analyze your state and suggest the best action.

## Workflows

### Feature Development Flow
1. Create branch: `/git-branch add feature-name`
2. Make changes to your code
3. Commit when ready: `/git-commit`
4. Push and create PR: `/git-push`
5. Update after feedback: make changes → `/git-push` (updates PR)

### Bug Fix Flow
1. Create branch: `/git-branch fix bug-description`
2. Fix the bug
3. Complete workflow: `/git-push`

### Sync and Update Flow
1. Rebase on main: `/git-rebase main`
2. Resolve conflicts if needed (guided by git-conflict-resolver)
3. Force push: `/git-push`

## Error Handling

All agents follow a consistent error handling pattern:
- Clear status indicators: `[SUCCESS]`, `[FAILED]`, `[PARTIAL]`, `[INFO]`
- Specific cause explanation
- Impact assessment
- Actionable solutions
- Current state summary

## Best Practices

1. **Use `/git-push` for complete workflows** - It handles everything from commit to PR
2. **Let the coordinator help** - Use `/git-workflow` when unsure what to do
3. **Branch naming matters** - Descriptive branch names improve collaboration
4. **Atomic commits** - Let git-commit-specialist group related changes
5. **Review before force push** - Always review suggested actions during rebase

## License

MIT