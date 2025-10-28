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

### pragmatic-code-reviewer

Thorough code review agent that balances engineering excellence with development velocity.

**Installation:**
```bash
/plugin install pragmatic-code-reviewer
```

**Usage:**
```bash
/pragmatic-code-review
```

**Key Features:**
- Pragmatic Quality Framework with FECE methodology
- MoSCoW prioritization (Must/Should/Could Have)
- Security, performance, and architecture analysis
- Context7 MCP integration for library documentation

[View full documentation](./plugins/pragmatic-code-reviewer/README.md)

## License

MIT
