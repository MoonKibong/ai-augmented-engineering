# Getting Started with AI Agents

> **Purpose**: Introduction to AI-assisted development and first steps for using Cursor, Claude, and Windsurf.

**Last Updated**: 2025-12-15 
**Audience**: Developers new to AI-assisted coding

---

## What Are AI Agents?

AI agents are AI-powered coding assistants integrated into your development environment. They can:

- **Understand your codebase** through context documents
- **Generate code** following your patterns and conventions
- **Answer questions** about your architecture and decisions
- **Refactor code** while maintaining consistency
- **Debug issues** by analyzing error messages and code
- **Write documentation** following your standards

### Key Agents

| Agent | Platform | Best For |
|-------|----------|----------|
| **Cursor** | Desktop IDE | Full IDE experience, inline editing, chat |
| **Claude** | Desktop app (Claude Code) | Deep code analysis, documentation, complex refactoring |
| **Windsurf** | Desktop IDE | Modern workflow, AI-first development |

---

## Why Use AI Agents?

### Productivity Gains

- **Faster development**: Generate boilerplate, implement patterns, write tests
- **Consistent code**: Follow established patterns automatically
- **Better documentation**: Keep docs up-to-date with code changes
- **Learning tool**: Understand new patterns and best practices

### Quality Improvements

- **Pattern enforcement**: AI agents follow your documented patterns
- **Error prevention**: Catch common mistakes before they happen
- **Code review**: Get instant feedback on code quality
- **Architectural consistency**: Maintain design decisions across the codebase

### Real-World Impact

Based on the Starshare project experience:
- **Reduced boilerplate**: 70% less time on repetitive code
- **Faster onboarding**: New developers productive in days, not weeks
- **Better documentation**: Living docs that stay current
- **Pattern consistency**: 21+ documented patterns followed automatically

---

## Prerequisites

### Required Knowledge

- **Programming fundamentals**: Variables, functions, control flow
- **Your tech stack**: Language, framework, libraries you're using
- **Version control**: Git basics (commit, push, pull)
- **IDE basics**: Opening files, running code, debugging

### Required Tools

- **Git**: Version control system
- **Code editor/IDE**: Your preferred development environment
- **AI agent**: Cursor, Claude Code, or Windsurf installed
- **Terminal**: Command line access

### Optional but Recommended

- **Markdown knowledge**: For writing context documents
- **Architecture understanding**: Know your project's structure
- **Documentation tools**: Markdown editor, diagram tools

---

## Choosing the Right Agent

### Cursor

**Choose Cursor if:**
- ✅ You want a full IDE experience
- ✅ You prefer inline code editing
- ✅ You work primarily in one codebase
- ✅ You want chat + Composer features
- ✅ You need file navigation and search

**Setup**: Install Cursor IDE, create `.cursorrules` file

**Learn more**: [Cursor Guide](../agents/cursor.md)

### Claude (Claude Code)

**Choose Claude if:**
- ✅ You need deep code analysis
- ✅ You're writing documentation
- ✅ You're doing complex refactoring
- ✅ You want conversational AI assistance
- ✅ You work across multiple projects

**Setup**: Install Claude Desktop, add `CLAUDE.md` to projects

**Learn more**: [Claude Guide](../agents/claude.md)

### Windsurf

**Choose Windsurf if:**
- ✅ You want a modern, AI-first IDE
- ✅ You prefer cloud-based workflows
- ✅ You want integrated AI features
- ✅ You're starting new projects

**Setup**: Install Windsurf IDE, configure project settings

**Learn more**: [Windsurf Guide](../agents/windsurf.md)

### Using Multiple Agents

**You can use multiple agents!** Each has strengths:

- **Cursor**: Day-to-day coding, quick edits
- **Claude**: Deep analysis, documentation, complex tasks
- **Windsurf**: Modern workflows, cloud collaboration

**Tip**: Use the same context documents across agents for consistency.

---

## First Steps

### Step 1: Install Your Agent

1. **Download and install** your chosen agent:
   - [Cursor](https://cursor.com/)
   - [Claude Desktop](https://claude.ai/download)
   - [Windsurf](https://code.windsurf.ai/)

2. **Authenticate** with your account

3. **Open your project** in the agent

### Step 2: Create Your First Context Document

**For new projects**: See [Starting from Scratch](../scenarios/starting-from-scratch.md)

**For existing projects**: See [Migrating Existing Projects](../scenarios/migrating-existing-projects.md)

**Quick start**: Create a simple context file:

```markdown
# Project Context

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js + Express
- Database: PostgreSQL

## Key Patterns
- Feature-based folder structure
- RESTful API conventions
- TypeScript strict mode

## Important Rules
- Never commit API keys
- Always validate user input
- Use TypeScript types, not `any`
```

### Step 3: Test the Agent

1. **Ask a question** about your codebase
2. **Request code generation** following your patterns
3. **Try a refactoring** task
4. **Generate documentation** for a function

**Example prompts**:
- "Explain how authentication works in this project"
- "Create a new API endpoint following our patterns"
- "Refactor this component to use hooks"
- "Document this function with JSDoc"

### Step 4: Iterate and Improve

- **Refine your context document** based on agent responses
- **Add more patterns** as you discover them
- **Document decisions** as you make them
- **Link to detailed docs** for complex topics

---

## Understanding Context Documents

### What Are Context Documents?

Context documents are files that provide AI agents with:
- **Project overview**: Tech stack, architecture, structure
- **Patterns and conventions**: How code should be written
- **Rules and constraints**: Security, performance, quality standards
- **Domain knowledge**: Business logic, relationships, workflows

### Common Context Files

| File | Agent | Purpose |
|------|-------|---------|
| `.cursorrules` | Cursor | Cursor-specific rules and patterns |
| `CLAUDE.md` | Claude | Comprehensive project context |
| `.windsurf/rules/global_rules.md` | Windsurf | Comprehensive project context |
| `docs/README.md` | Any | Documentation navigation |

**Tip** Create a project specific context file, e.g., MY_PROJECT_CONTEXT.md. And create 3 symbolic links each of which will serve as the root context file for each agent.
E.g.,

```sh
ln -s MY_PROJECT_CONTEXT.md .cursorrules.md
ln -s MY_PROJECT_CONTEXT.md CLAUDE.md
ln -s MY_PROJECT_CONTEXT.md .windsurf/rules/global_rules.md
```

### Key Principles

1. **Keep main file concise**: ~400 lines, link to details
2. **Progressive disclosure**: Summary → detailed docs
3. **Living documents**: Update as code evolves
4. **One source of truth**: Don't duplicate information

**Learn more**: [Writing Effective Context Documents](../context-documents/README.md)

---

## Common Workflows

### Daily Development

1. **Start your agent** and open your project
2. **Review context** if working on new area
3. **Ask questions** before coding  
   **Example prompts**:  
   - "Summarize the auth flow and entry points I should read"  
   - "Which patterns apply to adding a paginated list in this codebase?"  
   - "Where are examples of our form + Zod validation pattern?"  
   - "What tests should I update if I change the tasks API?"
4. **Generate code** following patterns
5. **Review and refine** generated code
6. **Update context** if patterns change  
   **Example prompts**:  
   - "Add a note to our context doc about the new cache invalidation rule we just used"  
   - "Draft a short summary for CLAUDE.md linking to the new pattern doc"  
   - "Suggest wording to record today's decision on error handling retries"  
   - "List which sections of `.cursorrules` should be updated after this refactor"

### Adding New Features

1. **Plan the feature** with the agent
2. **Check existing patterns** in context docs
3. **Generate initial code** structure
4. **Implement incrementally** with agent help
5. **Document the feature** as you build
6. **Update patterns** if new pattern emerges

### Refactoring

1. **Analyze current code** with agent
2. **Identify patterns** to apply
3. **Plan refactoring** steps
4. **Execute incrementally** with agent
5. **Update documentation** as you go
6. **Verify patterns** still work

### Debugging

1. **Describe the issue** to the agent
2. **Share error messages** and relevant code
3. **Ask for analysis** of root cause
4. **Generate fix** following patterns
5. **Test the solution**
6. **Document the fix** if non-trivial

---

## Expectations and Limitations

### What AI Agents Do Well

✅ **Pattern following**: Excellent at following documented patterns  
✅ **Boilerplate generation**: Fast at repetitive code  
✅ **Code transformation**: Good at refactoring and migrations  
✅ **Documentation**: Great at explaining and documenting code  
✅ **Question answering**: Understands codebase context  

### What AI Agents Struggle With

❌ **Creative problem solving**: May suggest generic solutions  
❌ **Business logic**: Needs domain knowledge in context  
❌ **Performance optimization**: May not optimize without guidance  
❌ **Security**: Follows patterns but may miss edge cases  
❌ **Testing**: May generate tests that don't catch real bugs  

### Best Practices

1. **Always review** generated code before committing
2. **Test thoroughly** - AI agents can introduce bugs
3. **Update context** when patterns change
4. **Ask questions** when unsure
5. **Iterate** - first generation is rarely perfect

---

## Next Steps

### For New Projects

1. ✅ Read this guide (you're here!)
2. → [Writing Effective Context Documents](../context-documents/README.md)
3. → [Starting from Scratch](../scenarios/starting-from-scratch.md)
4. → [Agent-Specific Guides](../agents/cursor.md)

### For Existing Projects

1. ✅ Read this guide (you're here!)
2. → [Writing Effective Context Documents](../context-documents/README.md)
3. → [Migrating Existing Projects](../scenarios/migrating-existing-projects.md)
4. → [Agent-Specific Guides](../agents/cursor.md)

### Advanced Topics

- [Documentation Patterns](../advanced/documentation-patterns.md)
- [Collaboration Workflows](../advanced/collaboration-workflows.md)
- [Troubleshooting](../advanced/troubleshooting.md)

---

## Quick Reference

### Essential Files

```
your-project/
├── .cursorrules          # Cursor rules (if using Cursor)
├── CLAUDE.md             # Claude context (if using Claude)
├── README.md             # Project overview
└── docs/
    ├── README.md         # Documentation index
    ├── patterns/         # Pattern documentation
    └── features/         # Feature documentation
```

### Key Commands

**Cursor**:
- `Cmd/Ctrl + K`: Inline edit
- `Cmd/Ctrl + L`: Chat
- `Cmd/Ctrl + I`: Composer

**Claude**:
- Open Claude Desktop
- Add project folder
- Start conversation

**Windsurf**:
- Check Windsurf documentation for shortcuts

---

## Questions?

- **General questions**: See [Troubleshooting](../advanced/troubleshooting.md)
- **Context documents**: See [Writing Effective Context Documents](../context-documents/README.md)
- **Agent-specific**: See agent guides in [agents/](../agents/)
- **Real-world examples**: Study Starshare project at `/Users/kibong/development/starshare-app`

---

**Ready to start?** → [Writing Effective Context Documents](../context-documents/README.md)

