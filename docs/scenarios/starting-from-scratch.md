# Starting from Scratch with AI Agents

> **Purpose**: Step-by-step guide for building a new project from the ground up using AI agents (Cursor, Claude, Windsurf).

**Last Updated**: 2025-12-15
**Audience**: Developers starting new projects

---

## Overview

Building a new project with AI agents allows you to:
- Establish patterns from the beginning
- Create comprehensive context documents as you build
- Maintain consistency from day one
- Build documentation alongside code

**This guide covers**:
1. Initial project setup
2. Creating your first context document
3. Iterative development workflow
4. Pattern documentation as you build
5. Common patterns and pitfalls

---

## Prerequisites

Before starting:
- ✅ Read [Getting Started Guide](../getting-started/README.md)
- ✅ Read [Writing Effective Context Documents](../context-documents/README.md)
- ✅ Choose your AI agent (Cursor, Claude, or Windsurf)
- ✅ Have your tech stack decided (or ready to decide with AI help)

---

## Phase 1: Project Initialization

### Step 1: Create Project Structure

**With AI Agent**:
```
Prompt: "Create a new [React/Node.js/etc.] project with the following structure:
- Feature-based folder organization
- TypeScript configuration
- Testing setup
- Documentation directory"
```

**Manual alternative**:
```bash
mkdir my-project
cd my-project
npm init -y  # or equivalent for your stack
mkdir -p src docs/patterns docs/features
```

### Step 2: Initialize Version Control

```bash
git init
echo "node_modules/" >> .gitignore
echo ".env" >> .gitignore
echo "dist/" >> .gitignore
git add .
git commit -m "Initial project setup"
```

### Step 3: Set Up Basic Configuration

**With AI Agent**:
```
Prompt: "Set up [TypeScript/ESLint/Prettier/etc.] configuration following best practices for [your tech stack]"
```

**Key files to create**:
- `tsconfig.json` (if TypeScript)
- `.eslintrc` or `eslint.config.js`
- `.prettierrc` (if using Prettier)
- `package.json` with dependencies

---

## Phase 2: Create Your First Context Document

### Step 1: Create Main Context File

**For Cursor**: Create `.cursorrules`  
**For Claude**: Create `CLAUDE.md`  
**For both**: Create both files with similar content

**Initial structure**:
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

[Add security rules as you discover them]

---

## Core Patterns

[Add patterns as you establish them]

---

## Architecture

[Document structure as you build]

---

**Version**: 0.1 | **Updated**: YYYY-MM-DD
```

### Step 2: Create Documentation Structure

```bash
mkdir -p docs/patterns docs/features docs/completed
touch docs/README.md
```

**Initial `docs/README.md`**:
```markdown
# Project Documentation

## Patterns
- [Add patterns as you create them]

## Features
- [Add features as you build them]

## Quick Reference
- [Add quick reference items]
```

### Step 3: Document Initial Decisions

**With AI Agent**:
```
Prompt: "Based on our project setup, document the initial architectural decisions:
- Folder structure
- Naming conventions
- Tech stack choices
- Development workflow"
```

**Add to context document**:
- Why you chose your tech stack
- Initial folder structure rationale
- Development workflow (git flow, etc.)

---

## Phase 3: Build Your First Feature

### Step 1: Plan the Feature

**With AI Agent**:
```
Prompt: "I want to build a [feature name] feature. Help me plan:
1. What components/files will I need?
2. What patterns should I follow?
3. What's the data flow?
4. What API endpoints (if any)?"
```

**Document the plan**:
- Create `docs/features/FEATURE_NAME.md`
- Add to context document if it establishes a pattern

### Step 2: Generate Initial Code Structure

**With AI Agent**:
```
Prompt: "Generate the initial code structure for [feature name] following our patterns:
- Create necessary files
- Set up API layer (if needed)
- Create component structure
- Add TypeScript types"
```

**Review generated code**:
- Does it follow your patterns?
- Are there improvements needed?
- Should this become a pattern?

### Step 3: Implement Incrementally

**Workflow**:
1. **Ask AI agent** to implement a small piece
2. **Review and test** the code
3. **Refine** if needed
4. **Document** any new patterns
5. **Repeat** for next piece

**Example prompts**:
- "Implement the API endpoint for [feature]"
- "Create the form component for [feature]"
- "Add validation using Zod"
- "Implement error handling"

### Step 4: Document Patterns as They Emerge

**When to document a pattern**:
- ✅ You've used it in 2+ places
- ✅ It solves a recurring problem
- ✅ It has clear do's and don'ts

**With AI Agent**:
```
Prompt: "I've noticed I'm using [pattern] in multiple places. 
Create a pattern document following our documentation template:
- Problem it solves
- Code examples
- Common pitfalls
- Related patterns"
```

**Update main context file**:
- Add brief summary of pattern
- Link to detailed pattern doc

---

## Phase 4: Establish Core Patterns

### Common Patterns to Establish Early

#### 1. Data Fetching Pattern

**When**: You make your first API call

**Document**:
- How to structure API calls
- Error handling approach
- Loading states
- Caching strategy

**Example pattern**:
```markdown
## Data Fetching Pattern

### Query Pattern
```typescript
export const queryKey = 'items-list'
export const itemsQueryOptions = (params?) => queryOptions({
  queryKey: [queryKey, params],
  queryFn: () => getItems(params),
})
```

See `docs/patterns/DATA_FETCHING.md` for details.
```

#### 2. Error Handling Pattern

**When**: You handle your first error

**Document**:
- Error types and handling
- User-facing error messages
- Error logging
- Retry strategies

#### 3. Form Handling Pattern

**When**: You create your first form

**Document**:
- Form library choice (React Hook Form, Formik, etc.)
- Validation approach (Zod, Yup, etc.)
- Submission patterns
- Error display

#### 4. State Management Pattern

**When**: You need shared state

**Document**:
- When to use local state
- When to use global state
- State management library (if any)
- State persistence

### Pattern Documentation Workflow

1. **Use pattern** in 2+ places
2. **Recognize** it's a pattern
3. **Create pattern doc** with AI agent help
4. **Update main context** with link
5. **Refactor existing code** to follow pattern

---

## Phase 5: Iterative Development

### Daily Workflow

1. **Start session**:
   - Open project in AI agent
   - Review context if needed

2. **Plan work**:
   - What feature/issue to work on?
   - What patterns apply?
   - What's the approach?

3. **Implement with AI**:
   - Ask for code generation
   - Review and refine
   - Test thoroughly

4. **Document as you go**:
   - New patterns → pattern doc
   - New features → feature doc
   - Bug fixes → update relevant docs

5. **End session**:
   - Commit changes
   - Update "Last Updated" dates
   - Note any patterns that emerged

### Feature Development Workflow

1. **Plan feature**:
   ```
   Prompt: "I want to build [feature]. Help me plan the implementation."
   ```

2. **Check existing patterns**:
   - Review context document
   - Check pattern docs
   - Identify reusable patterns

3. **Generate structure**:
   ```
   Prompt: "Generate the code structure for [feature] following our patterns."
   ```

4. **Implement incrementally**:
   - Small, testable pieces
   - Review each piece
   - Refine as needed

5. **Document feature**:
   - Create feature doc
   - Update main context if needed
   - Document any new patterns

6. **Review and refine**:
   - Code review (self or team)
   - Refactor if needed
   - Update documentation

---

## Common Patterns for New Projects

### Project Structure Pattern

**Early decision**: How to organize code

**Options**:
- Feature-based: `src/features/[feature]/`
- Layer-based: `src/components/`, `src/services/`, etc.
- Domain-driven: `src/domains/[domain]/`

**Document your choice**:
```markdown
## Architecture

### Folder Structure
- **Features**: `src/features/{name}/` (self-contained)
- **Shared**: `src/shared/` (utilities, types)
- **Components**: `src/components/` (reusable UI)
```

### API Client Pattern

**Early decision**: How to make API calls

**Options**:
- Fetch API
- Axios
- TanStack Query
- Custom wrapper

**Document your choice**:
```markdown
## API Client Pattern

We use [library] for API calls with the following pattern:
[Code example]

See `docs/patterns/API_CLIENT.md` for details.
```

### Authentication Pattern

**Early decision**: How to handle auth

**Document**:
- Auth library/approach
- Token storage
- Protected routes
- Session management

**Critical**: Document security rules first!

---

## Pitfalls to Avoid

### ❌ Pitfall 1: Skipping Context Documents

**Problem**: Start coding without context documents.

**Solution**: Create basic context document before writing code.

**Why**: AI agents need context to generate good code.

### ❌ Pitfall 2: Not Documenting Patterns Early

**Problem**: Wait until patterns are "perfect" to document.

**Solution**: Document patterns as they emerge, refine later.

**Why**: Patterns evolve, documentation should too.

### ❌ Pitfall 3: Too Much Detail in Main Context File

**Problem**: Put everything in main context file.

**Solution**: Keep main file ~400 lines, link to details.

**Why**: Easier to scan and maintain.

### ❌ Pitfall 4: Not Updating Documentation

**Problem**: Documentation gets outdated.

**Solution**: Update docs as code changes, set reminders.

**Why**: Outdated docs are worse than no docs.

### ❌ Pitfall 5: Generic Patterns

**Problem**: Use generic patterns without customization.

**Solution**: Adapt patterns to your project's needs.

**Why**: Your project has unique requirements.

---

## Example: Building a Todo App

### Phase 1: Setup

```bash
# Create project
npx create-react-app todo-app --template typescript
cd todo-app

# Create docs structure
mkdir -p docs/patterns docs/features
```

### Phase 2: Initial Context Document

**`.cursorrules`**:
```
# Todo App - Cursor Rules

## Tech Stack
- Frontend: React + TypeScript
- State: React Query for server state
- Forms: React Hook Form + Zod

## Patterns
- Feature-based structure: src/features/[feature]/
- API calls via React Query
- Form validation with Zod schemas
```

### Phase 3: First Feature (Todo List)

**With AI Agent**:
```
Prompt: "Create a todo list feature with:
- API layer using React Query
- Form for adding todos
- List component for displaying todos
- Follow our feature-based structure"
```

**Generated structure**:
```
src/features/todos/
├── api/
│   ├── queries.ts
│   └── mutations.ts
├── components/
│   ├── todo-list.tsx
│   └── todo-form.tsx
├── data/
│   └── schema.ts
└── index.tsx
```

### Phase 4: Document Pattern

**After using React Query in 2+ places**:

**Create `docs/patterns/REACT_QUERY_PATTERN.md`**:
```markdown
# React Query Pattern

## Overview
We use React Query for all server state management.

## Pattern
[Code examples]

## Common Pitfalls
[Pitfalls and solutions]
```

**Update `.cursorrules`**:
```markdown
## Core Patterns

### React Query
[Brief example]
See `docs/patterns/REACT_QUERY_PATTERN.md` for details.
```

---

## Checklist: Starting from Scratch

### Initial Setup
- [ ] Project structure created
- [ ] Version control initialized
- [ ] Basic configuration files set up
- [ ] Documentation directories created

### Context Documents
- [ ] Main context file created (.cursorrules or CLAUDE.md)
- [ ] Initial project overview documented
- [ ] Tech stack documented
- [ ] Documentation index created

### First Feature
- [ ] Feature planned
- [ ] Code structure generated
- [ ] Feature implemented
- [ ] Feature tested
- [ ] Feature documented

### Patterns Established
- [ ] Data fetching pattern documented
- [ ] Error handling pattern documented
- [ ] Form handling pattern documented (if applicable)
- [ ] State management pattern documented

### Ongoing
- [ ] Patterns documented as they emerge
- [ ] Context documents updated regularly
- [ ] Documentation stays current with code

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Start building your project
3. → Create context documents as you go
4. → Document patterns as they emerge
5. → Reference [Agent-Specific Guides](../agents/cursor.md) as needed
6. → See [Advanced Topics](../advanced/documentation-patterns.md) for more

---

## Resources

- **Context Documents Guide**: [Writing Effective Context Documents](../context-documents/README.md)
- **Real-World Example**: Study Starshare project structure
- **Agent Guides**: [Cursor](../agents/cursor.md), [Claude](../agents/claude.md), [Windsurf](../agents/windsurf.md)

---

**Ready to start?** Create your project and begin with Phase 1!

