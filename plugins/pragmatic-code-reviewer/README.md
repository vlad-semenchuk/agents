# Pragmatic Code Reviewer

Thorough code review agent that balances engineering excellence with development velocity.

## Installation

```bash
/plugin install pragmatic-code-reviewer
```

## Usage

```bash
/pragmatic-code-reviewer:review
```

## Features

- **Pragmatic Quality Framework**: Balance rigorous engineering standards with development speed
- **FECE Methodology**: Fact, Empathy, Context, Example - structured, actionable feedback
- **MoSCoW Prioritization**: Clear Must/Should/Could Have categorization
- **Comprehensive Analysis**: Security, performance, architecture, maintainability
- **Context7 Integration**: Up-to-date library documentation lookup

## What It Reviews

### Must Have (Blocks Merge)
- Architectural design & integrity
- Functionality & correctness
- Security (authentication, authorization, input validation, XSS, SQLi prevention)
- Critical tests for auth, payments, data writes
- N+1 queries in critical paths

### Should Have (Prevents Tech Debt)
- DRY violations (rework amplifiers)
- High complexity (>3 nesting levels)
- Code coupling and maintainability
- Testing strategy for medium-risk features
- Performance in non-critical paths

### Could Have (Optional)
- Code style improvements
- Minor refactoring suggestions
- Documentation enhancements

## Review Philosophy

1. **Net Positive > Perfection**: Approve if change improves overall code health
2. **Focus on Substance**: Architecture, design, business logic, security, complex interactions
3. **Grounded in Principles**: SOLID, DRY, KISS, YAGNI - technical facts, not opinions
4. **Rework Cost Awareness**: Emphasize issues that multiply future maintenance burden

## Output Format

Each review includes:
- **Summary**: Overall recommendation (Approve/Request Changes/Needs Discussion)
- **Health Assessment**: How the change impacts codebase (Improves/Neutral/Degrades)
- **Risk Level**: High/Medium/Low
- **Findings**: Structured FECE format with specific file locations and code examples
- **Actionable Fixes**: Clear, prescriptive solutions with acceptance criteria

## Dependencies

- **Context7 MCP Server**: Automatically installed for library documentation lookup

## Example Use Cases

- After implementing a new API endpoint (security-critical)
- After refactoring a complex service (performance-critical)
- Before merging a feature branch (complete feature review)
- Regular code quality checks during development

## License

MIT