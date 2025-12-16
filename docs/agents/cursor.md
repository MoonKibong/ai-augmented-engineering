# Cursor IDE Guide

> **Purpose**: Comprehensive guide for using Cursor IDE with AI agents for software development.

**Last Updated**: 2025-12-15
**Agent**: Cursor IDE

---

## Overview

Cursor is a full-featured IDE built on VS Code with integrated AI capabilities. It provides:
- **Inline editing**: AI-powered code generation and editing
- **Chat**: Conversational AI assistance
- **Composer**: Multi-file code generation
- **Context awareness**: Understands your codebase through `.cursorrules`

---

## Setup

### Installation

1. **Download Cursor**:
   - Visit [cursor.com](https://cursor.com)
   - Download for your platform (macOS, Windows, Linux)
   - Install the application

2. **Sign In**:
   - Create account or sign in
   - Choose subscription plan (free tier available)

3. **Open Your Project**:
   - File → Open Folder
   - Select your project directory

### Initial Configuration

1. **Create `.cursorrules` file**:
   ```bash
   touch .cursorrules
   ```

2. **Add basic rules**:
   ```markdown
   # Cursor Rules for [Project Name]

   ## Tech Stack
   - [Your tech stack]

   ## Patterns
   - [Your patterns]

   ## Rules
   - [Your rules]
   ```

3. **Configure settings** (optional):
   - Cursor → Settings
   - Adjust AI model preferences
   - Configure inline edit behavior

---

## Key Features

### 1. Inline Editing (`Cmd/Ctrl + K`)

**What it does**: Generate or edit code inline based on your cursor position.

**How to use**:
1. Place cursor where you want code
2. Press `Cmd/Ctrl + K`
3. Type your request
4. Review generated code
5. Accept or modify

**Example prompts**:
- "Create a React component for user profile"
- "Add error handling to this function"
- "Refactor this to use hooks"
- "Add TypeScript types"

**Best practices**:
- ✅ Be specific about what you want
- ✅ Reference existing patterns
- ✅ Review generated code before accepting
- ✅ Iterate if first result isn't perfect

### 2. Chat (`Cmd/Ctrl + L`)

**What it does**: Conversational AI assistant for questions and discussions.

**How to use**:
1. Press `Cmd/Ctrl + L`
2. Type your question or request
3. Review response
4. Follow up with more questions

**Example prompts**:
- "Explain how authentication works in this project"
- "What patterns should I use for API calls?"
- "Help me debug this error"
- "Review this code for potential issues"

**Best practices**:
- ✅ Ask specific questions
- ✅ Reference file paths when relevant
- ✅ Use for understanding, not just generation
- ✅ Follow up to clarify

### 3. Composer (`Cmd/Ctrl + I`)

**What it does**: Generate code across multiple files with full context.

**How to use**:
1. Press `Cmd/Ctrl + I`
2. Describe what you want to build
3. Select files to include in context
4. Review generated changes
5. Accept or modify

**Example prompts**:
- "Create a new feature for user settings with form, API, and validation"
- "Refactor authentication to use JWT tokens"
- "Add error handling to all API endpoints"

**Best practices**:
- ✅ Include relevant files in context
- ✅ Be clear about file structure
- ✅ Review all changes before accepting
- ✅ Test thoroughly after generation

---

## Context Documents

### `.cursorrules` File

**Location**: Project root

**Purpose**: Provides Cursor with project context, patterns, and rules.

**Format**: Plain text or Markdown

**Structure**:
```markdown
# Cursor Rules for [Project Name]

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js + Express
- Database: PostgreSQL

## Project Structure
- Features: src/features/[feature]/
- Shared: src/shared/
- Components: src/components/

## Patterns
- Use React Query for data fetching
- Validate forms with Zod
- Handle errors with try/catch

## Rules
- Never use `any` type
- Always handle errors
- Use TypeScript strict mode
```

**Best practices**:
- ✅ Keep it concise but comprehensive
- ✅ Update as patterns evolve
- ✅ Reference detailed docs with links
- ✅ Prioritize security rules first

**Learn more**: See [Writing Effective Context Documents](../context-documents/README.md)

---

## Workflows

### Daily Development Workflow

1. **Open project** in Cursor
2. **Review context** if working on new area (read `.cursorrules`)
3. **Use Chat** to understand existing code
4. **Use Inline Edit** for quick changes
5. **Use Composer** for multi-file changes
6. **Review and test** all generated code
7. **Update `.cursorrules`** if patterns change

### Feature Development Workflow

1. **Plan with Chat**:
   ```
   "I want to build [feature]. Help me plan the implementation."
   ```

2. **Generate structure with Composer**:
   ```
   "Create the file structure for [feature] following our patterns."
   ```

3. **Implement with Inline Edit**:
   - Generate components
   - Add API calls
   - Implement logic

4. **Refine with Chat**:
   ```
   "Review this implementation and suggest improvements."
   ```

5. **Document patterns** if new patterns emerge

### Refactoring Workflow

1. **Analyze with Chat**:
   ```
   "Help me understand this code and identify refactoring opportunities."
   ```

2. **Plan refactoring**:
   ```
   "Plan how to refactor this to follow our [pattern] pattern."
   ```

3. **Execute with Composer**:
   ```
   "Refactor these files to use [new pattern]."
   ```

4. **Review changes**:
   - Check all modified files
   - Test functionality
   - Update documentation

### Debugging Workflow

1. **Describe issue to Chat**:
   ```
   "I'm getting this error: [error message]. Help me debug."
   ```

2. **Share relevant code**:
   - Select code
   - Ask Chat to analyze

3. **Generate fix**:
   ```
   "Fix this bug following our error handling pattern."
   ```

4. **Test solution**:
   - Verify fix works
   - Check for edge cases
   - Update tests if needed

---

## Best Practices

### Prompt Engineering

**Be specific**:
- ❌ "Fix this"
- ✅ "Add error handling to this API call using our try/catch pattern"

**Reference patterns**:
- ❌ "Create a form"
- ✅ "Create a form following our React Hook Form + Zod pattern"

**Provide context**:
- ❌ "Add validation"
- ✅ "Add Zod validation to this form, checking that email is required and valid"

### Code Review

**Always review generated code**:
- ✅ Check for bugs
- ✅ Verify it follows patterns
- ✅ Test functionality
- ✅ Check performance implications

**Don't blindly accept**:
- ❌ Accepting without review
- ✅ Review, test, then accept

### Context Management

**Keep `.cursorrules` updated**:
- ✅ Add new patterns as they emerge
- ✅ Update when architecture changes
- ✅ Remove outdated information
- ✅ Link to detailed docs

**Use file context**:
- ✅ Include relevant files in Composer
- ✅ Reference file paths in Chat
- ✅ Show code examples when asking questions

---

## Advanced Features

### Codebase Indexing

Cursor indexes your codebase to understand context better.

**How it works**:
- Automatically indexes on project open
- Updates as files change
- Used for context in all AI features

**Tips**:
- Large codebases may take time to index
- Indexing happens in background
- Can manually trigger re-index if needed

### Multi-File Editing

Composer can edit multiple files simultaneously.

**When to use**:
- Creating new features
- Refactoring across files
- Updating related components

**Best practices**:
- ✅ Review all file changes
- ✅ Test after multi-file edits
- ✅ Commit related changes together

### Code Suggestions

Cursor provides inline suggestions as you type.

**How it works**:
- Analyzes your code context
- Suggests completions
- Learns from your patterns

**Customization**:
- Adjust suggestion frequency
- Configure when to show suggestions
- Train on your codebase patterns

---

## Troubleshooting

### Issue: Generated code doesn't follow patterns

**Solution**:
- Update `.cursorrules` with clearer pattern descriptions
- Include code examples in rules
- Reference pattern docs in rules

### Issue: AI doesn't understand context

**Solution**:
- Improve `.cursorrules` file
- Include more context in prompts
- Use Composer with relevant files selected

### Issue: Suggestions are too generic

**Solution**:
- Add more project-specific context to `.cursorrules`
- Reference existing code in prompts
- Use more specific prompts

### Issue: Performance issues

**Solution**:
- Reduce codebase size for indexing
- Use `.cursorignore` for large files
- Adjust AI model settings

---

## Integration with Other Tools

### Git Integration

Cursor has built-in Git support:
- View diffs
- Stage and commit changes
- Resolve conflicts

**Workflow**:
1. Generate code with Cursor
2. Review changes in Git view
3. Stage and commit
4. Push to remote

### Terminal Integration

Built-in terminal for running commands:
- Run tests
- Start dev servers
- Execute build commands

### Extension Support

Cursor supports VS Code extensions:
- Install extensions from marketplace
- Use existing VS Code extensions
- Customize your environment

---

## Comparison with Other Agents

### vs Claude Code

| Feature | Cursor | Claude Code |
|--------|--------|-------------|
| IDE Experience | Full IDE | Desktop app |
| Inline Editing | ✅ Yes | ❌ No |
| Chat | ✅ Yes | ✅ Yes |
| Multi-file Editing | ✅ Composer | ✅ Yes |
| Codebase Indexing | ✅ Yes | ✅ Yes |

### vs Windsurf

| Feature | Cursor | Windsurf |
|--------|--------|----------|
| Platform | Desktop | Desktop/Cloud |
| Inline Editing | ✅ Yes | ✅ Yes |
| Chat | ✅ Yes | ✅ Yes |
| Context Files | `.cursorrules` | `.windsurf/` |

---

## Resources

- **Official Docs**: [docs.cursor.com](https://docs.cursor.com)
- **Context Documents**: [Writing Effective Context Documents](../context-documents/README.md)
- **Real-World Example**: Study Starshare's `.cursorrules` (if exists) or `STARSHARE.md`

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Install Cursor and set up your project
3. → Create `.cursorrules` file
4. → Try inline editing, chat, and composer
5. → Reference [Getting Started](../getting-started/README.md) for workflows

---

**Ready to use Cursor?** Install it and create your `.cursorrules` file!

