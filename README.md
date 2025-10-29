# Claude Code Plugins

A collection of production-ready Claude Code plugins for enhanced development workflows, code quality, and automation.

## Quick Start

### Adding the Marketplace

Add this marketplace to your Claude Code instance:

```bash
/plugin marketplace add vlad-semenchuk/agents
```

Verify the marketplace was added:

```bash
/plugin marketplace list
```

### Installing Plugins

Install any plugin from the marketplace:

```bash
/plugin install <plugin-name>
```

List all available plugins:

```bash
/plugin marketplace show vlad-semenchuk/agents
```

List all installed plugins:

```bash
/plugin list
```

## Available Plugins

### git-workflow

Smart git workflow orchestrator that analyzes current state and executes appropriate workflows with intelligent intent recognition.

**Installation:**
```bash
/plugin install git-workflow
```

**Usage:**
```bash
/git-workflow     # Smart orchestrator - analyzes state and executes appropriate workflow
/git-commit       # Create atomic commits with conventional format
/git-branch       # Create a new branch with smart naming
/git-push         # Complete push workflow (commit, push, create/update PR)
/git-pr           # Create or update pull request
/git-rebase       # Rebase current branch onto target
```

**Key Features:**
- Intelligent intent recognition from natural language
- Automated commit creation with conventional messages
- Complete push workflow with PR management
- Smart branch naming with type inference
- Conflict resolution assistance
- GitHub CLI integration for seamless PR operations

**Specialist Agents:**
- git-workflow-coordinator: Orchestrates workflows
- git-commit-specialist: Creates atomic commits
- git-pr-specialist: Manages pull requests
- git-conflict-resolver: Resolves merge conflicts

**Dependencies:**
- GitHub CLI (`gh`) - Required for PR operations

[View full documentation](./plugins/git-workflow/README.md)

### pragmatic-code-reviewer

Thorough code review agent that balances engineering excellence with development velocity.

**Installation:**
```bash
/plugin install pragmatic-code-reviewer
```

**Usage:**
```bash
/review
```

**Key Features:**
- Pragmatic Quality Framework with FECE methodology
- MoSCoW prioritization (Must/Should/Could Have)
- Security, performance, and architecture analysis
- Context7 MCP integration for library documentation

[View full documentation](./plugins/pragmatic-code-reviewer/README.md)

## License

MIT
