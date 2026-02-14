# Installing the Demiur CLI

The Demiur CLI allows you to manage your skills, agents, and instructions directly from your terminal. It's the perfect tool for integrating Demiur resources into your development workflow.

## Prerequisites

- **Go 1.21+** installed on your machine ([download Go](https://go.dev/dl/))
- A Demiur.ai account (free)

## Quick Installation

```bash
go install github.com/demiur-ai/demiur-cli@latest
```

The `demiur` binary will be automatically added to your `$GOPATH/bin`.

## Verify Installation

Check that the CLI is correctly installed:

```bash
demiur --version
```

You should see the current CLI version displayed.

## First-Time Setup

### Connect to Your Account

To use registry features (search, install, publish), log in:

```bash
demiur registry login
```

This command will open your browser to authenticate on Demiur.ai.

## Next Steps

- [Discover available commands](/documentation/cli/commands)
- [Create your first project](/documentation/cli/getting-started)


# Create Your First Project

This guide walks you through creating your first Demiur project in just a few minutes.

## Initialize a New Project

Create a new project with the `init` command:

```bash
demiur init my-agent
cd my-agent
```

This command generates a complete project structure:

```
my-agent/
├── demiur.yaml          # Project configuration
├── agent.md             # Your agent definition
├── instructions/        # Your rules and directives
│   └── base.md
├── skills/              # Local skills
└── prompts/             # Reusable prompts
```

### Available Templates

Choose a template based on your needs:

```bash
# Minimal template (default)
demiur init my-agent

# Full template with examples
demiur init my-agent --template full

# Claude Code template
demiur init my-agent --template claude-code
```

## Explore the Created Project

### The demiur.yaml File

This is the main configuration file for your project:

```yaml
name: my-agent
version: 1.0.0
description: Description of my agent
deployment_target: generic
```

### The agent.md File

Defines the behavior and capabilities of your agent:

```markdown
# My Agent

## Role

Describe your agent's role...

## Capabilities

- Capability 1
- Capability 2

## Behavior

How the agent should respond...
```

## Validate Your Project

Before publishing or using your project, validate it:

```bash
demiur validate
```

The CLI will check:
- Project structure
- File formats
- Required metadata
- Cross-references between resources

### Strict Mode

For more rigorous validation:

```bash
demiur validate --strict
```

## Next Steps

Now that your project is created:

1. **Add skills** from the registry
2. **Create your own instructions**
3. **Customize your agent**
4. **Share with the community**
