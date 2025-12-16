# Claude Code Guide

> **Purpose**: Comprehensive guide for using Claude (Claude Desktop / Claude Code) with AI agents for software development.

**Last Updated**: 2025-12-15
**Agent**: Claude (Anthropic)

---

## Overview

Claude Code (Claude Desktop) is a conversational AI assistant that can analyze code, generate documentation, and help with complex development tasks. It provides:
- **Deep code analysis**: Understand complex codebases
- **Documentation generation**: Create comprehensive docs
- **Conversational assistance**: Natural language interaction
- **Context awareness**: Understands your project through `CLAUDE.md`

---

## Setup

### Installation

1. **Download Claude Desktop**:
   - Visit [claude.ai/download](https://claude.ai/download)
   - Download for your platform (macOS, Windows)
   - Install the application

2. **Sign In**:
   - Create account or sign in
   - Choose subscription plan

3. **Add Project Folder**:
   - File → Add Folder
   - Select your project directory
   - Claude will index the codebase

### Initial Configuration

1. **Create `CLAUDE.md` file**:
   ```bash
   touch CLAUDE.md
   ```

2. **Add basic context**:
   ```markdown
   # [Project Name] - AI Assistant Context

   ## Project
   [Project overview]

   ## Tech Stack
   [Your tech stack]

   ## Patterns
   [Your patterns]
   ```

3. **Configure preferences** (optional):
   - Model selection (Claude 3.5 Sonnet, etc.)
   - Context window size
   - Response preferences

---

## Key Features

### 1. Code Analysis

**What it does**: Deep understanding of codebase structure, patterns, and relationships.

**How to use**:
1. Ask Claude to analyze code
2. Share files or code snippets
3. Get detailed analysis and suggestions

**Example prompts**:
- "Analyze the architecture of this codebase"
- "Identify patterns in these files"
- "Explain how authentication works"
- "Find inconsistencies in error handling"

**Best practices**:
- ✅ Share relevant files for context
- ✅ Ask specific questions
- ✅ Request code examples
- ✅ Follow up for clarification

### 2. Documentation Generation

**What it does**: Generate comprehensive documentation from code.

**How to use**:
1. Ask Claude to document code
2. Specify documentation type
3. Review and refine generated docs

**Example prompts**:
- "Document this API following our documentation patterns"
- "Create a pattern document for this code pattern"
- "Generate README for this feature"
- "Document the authentication flow"

**Best practices**:
- ✅ Reference your documentation patterns
- ✅ Provide examples of existing docs
- ✅ Review and refine generated docs
- ✅ Update as code changes

### 3. Code Generation

**What it does**: Generate code following your patterns and conventions.

**How to use**:
1. Describe what you want to build
2. Reference existing patterns
3. Review generated code
4. Iterate if needed

**Example prompts**:
- "Create a new API endpoint following our controller pattern"
- "Generate a React component using our component pattern"
- "Implement error handling following our error pattern"

**Best practices**:
- ✅ Reference `CLAUDE.md` for patterns
- ✅ Show examples of similar code
- ✅ Be specific about requirements
- ✅ Review generated code thoroughly

### 4. Refactoring Assistance

**What it does**: Help refactor code while maintaining functionality.

**How to use**:
1. Share code to refactor
2. Specify refactoring goals
3. Review proposed changes
4. Apply changes incrementally

**Example prompts**:
- "Refactor this to use our query pattern"
- "Improve this code following our patterns"
- "Migrate this from class to functional component"

**Best practices**:
- ✅ Refactor incrementally
- ✅ Test after each change
- ✅ Document new patterns
- ✅ Update `CLAUDE.md` if patterns change

---

## Context Documents

### `CLAUDE.md` File

**Location**: Project root

**Purpose**: Provides Claude with comprehensive project context.

**Format**: Markdown

**Structure**:
```markdown
# [Project Name] - AI Assistant Context

> **⚠️ MAINTENANCE**: Keep under **20KB** (~400 lines). 
> Move details to `docs/patterns/`. 
> Prioritize: security > patterns > structure.

## Project

| Component | Path | Stack |
|-----------|------|-------|
| Frontend | `/path/to/frontend` | [Your stack] |
| Backend | `/path/to/backend` | [Your stack] |

---

## CRITICAL: Security Rules

[Security patterns]

---

## Core Patterns

[Pattern summaries with links to detailed docs]

---

## Architecture

[Project structure]

---

## Documentation

- **Patterns**: `docs/patterns/` (N docs)
- **Index**: `docs/README.md`

---

**Version**: X.X | **Updated**: YYYY-MM-DD
```

**Best practices**:
- ✅ Keep main file ~400 lines
- ✅ Link to detailed pattern docs
- ✅ Update as patterns evolve
- ✅ Prioritize security rules first

**Learn more**: See [Writing Effective Context Documents](../context-documents/README.md)

---

## Workflows

### Daily Development Workflow

1. **Open Claude Desktop**
2. **Add project folder** (if not already added)
3. **Review `CLAUDE.md`** if working on new area
4. **Ask questions** about existing code
5. **Generate code** following patterns
6. **Review and refine** generated code
7. **Update `CLAUDE.md`** if patterns change

### Feature Development Workflow

1. **Plan with Claude**:
   ```
   "I want to build [feature]. Help me plan the implementation 
   following our patterns."
   ```

2. **Generate structure**:
   ```
   "Create the file structure for [feature] following our 
   feature-based organization pattern."
   ```

3. **Implement incrementally**:
   - Generate components
   - Add API calls
   - Implement logic
   - Ask for review

4. **Document feature**:
   ```
   "Document this feature following our feature documentation pattern."
   ```

5. **Update patterns** if new patterns emerge

### Documentation Workflow

1. **Identify what to document**:
   - New pattern
   - Feature specification
   - Bug fix

2. **Ask Claude to document**:
   ```
   "Create a pattern document for [pattern] following our 
   documentation template. Include examples from [files]."
   ```

3. **Review and refine**:
   - Check accuracy
   - Add missing details
   - Improve examples

4. **Update context**:
   - Add link to new doc in `CLAUDE.md`
   - Update documentation index

### Refactoring Workflow

1. **Analyze with Claude**:
   ```
   "Analyze this code and identify refactoring opportunities 
   to follow our patterns."
   ```

2. **Plan refactoring**:
   ```
   "Plan how to refactor this to use [pattern]. 
   Maintain all existing functionality."
   ```

3. **Execute incrementally**:
   ```
   "Refactor this file to use [pattern]. Show the changes."
   ```

4. **Review and test**:
   - Verify functionality
   - Check for regressions
   - Update documentation

---

## Best Practices

### Prompt Engineering

**Be specific and contextual**:
- ❌ "Document this"
- ✅ "Document this API endpoint following our API documentation pattern. Include request/response examples and error cases."

**Reference existing patterns**:
- ❌ "Create a form"
- ✅ "Create a form following our React Hook Form + Zod validation pattern. See `src/features/auth/components/login-form.tsx` for reference."

**Provide code context**:
- ✅ Share relevant files
- ✅ Reference existing implementations
- ✅ Show examples of similar code

### Code Review

**Always review generated code**:
- ✅ Check for bugs
- ✅ Verify it follows patterns
- ✅ Test functionality
- ✅ Check edge cases

**Iterate for improvement**:
- ✅ Ask for refinements
- ✅ Request alternative approaches
- ✅ Get explanations for decisions

### Context Management

**Keep `CLAUDE.md` updated**:
- ✅ Add new patterns as they emerge
- ✅ Update when architecture changes
- ✅ Remove outdated information
- ✅ Link to detailed docs

**Use file references**:
- ✅ Share relevant files in conversation
- ✅ Reference file paths in prompts
- ✅ Show code examples when asking questions

---

## Advanced Features

### Codebase Analysis

Claude can analyze entire codebases to understand:
- Architecture and structure
- Patterns and conventions
- Relationships between components
- Inconsistencies and improvements

**Example prompts**:
- "Analyze the entire codebase and identify all patterns being used"
- "Find all places where error handling is inconsistent"
- "Identify opportunities to apply our patterns"

### Pattern Documentation

Claude excels at creating pattern documentation:
- Pattern templates
- Real-world examples
- Common pitfalls
- Related patterns

**Example prompts**:
- "Create a pattern document for our query pattern following our template"
- "Document this pattern with examples from the codebase"
- "Create a pattern doc that includes common pitfalls"

### Complex Refactoring

Claude can help with large refactoring tasks:
- Analyze impact
- Plan migration
- Generate refactored code
- Update documentation

**Example prompts**:
- "Plan a migration from [old pattern] to [new pattern]"
- "Refactor all API endpoints to use our new pattern"
- "Help me migrate this codebase to TypeScript"

---

## Troubleshooting

### Issue: Claude doesn't understand context

**Solution**:
- Improve `CLAUDE.md` with more details
- Share relevant files in conversation
- Provide code examples
- Reference existing patterns

### Issue: Generated code doesn't follow patterns

**Solution**:
- Update `CLAUDE.md` with clearer pattern descriptions
- Include code examples in `CLAUDE.md`
- Reference pattern docs in prompts
- Show examples of correct implementations

### Issue: Documentation is too generic

**Solution**:
- Provide specific examples from codebase
- Reference your documentation patterns
- Ask for code examples in docs
- Review and refine generated docs

### Issue: Responses are too verbose

**Solution**:
- Ask for concise responses
- Specify format preferences
- Request bullet points or summaries
- Ask for code-only responses when appropriate

---

## Comparison with Other Agents

### vs Cursor

| Feature | Claude | Cursor |
|--------|--------|--------|
| Platform | Desktop app | Full IDE |
| Inline Editing | ❌ No | ✅ Yes |
| Chat | ✅ Yes | ✅ Yes |
| Code Analysis | ✅ Excellent | ✅ Good |
| Documentation | ✅ Excellent | ✅ Good |
| Multi-file Editing | ✅ Yes | ✅ Composer |

### vs Windsurf

| Feature | Claude | Windsurf |
|--------|--------|----------|
| Platform | Desktop app | Desktop/Cloud IDE |
| Inline Editing | ❌ No | ✅ Yes |
| Chat | ✅ Yes | ✅ Yes |
| Code Analysis | ✅ Excellent | ✅ Good |
| Context Files | `CLAUDE.md` | `.windsurf/` |

---

## Use Cases

### Best For

✅ **Deep code analysis**  
✅ **Documentation generation**  
✅ **Complex refactoring**  
✅ **Pattern identification**  
✅ **Architectural discussions**  

### Less Ideal For

❌ **Quick inline edits** (use Cursor)  
❌ **Real-time coding** (use Cursor/Windsurf)  
❌ **File navigation** (use IDE)  

---

## Resources

- **Official Docs**: [claude.ai](https://claude.ai)
- **Context Documents**: [Writing Effective Context Documents](../context-documents/README.md)
- **Real-World Example**: Study Starshare's `CLAUDE.md` or `STARSHARE.md`

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Install Claude Desktop
3. → Create `CLAUDE.md` file
4. → Try code analysis and documentation
5. → Reference [Getting Started](../getting-started/README.md) for workflows

---

**Ready to use Claude?** Install Claude Desktop and create your `CLAUDE.md` file!

