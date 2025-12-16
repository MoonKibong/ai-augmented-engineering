# Writing Effective Context Documents

> **Purpose**: Comprehensive guide on creating and maintaining context documents (CLAUDE.md, .cursorrules, etc.) that enable effective AI agent collaboration.

**Last Updated**: 2025-12-15
**Critical**: This is the most important document for AI agent success

---

## What Are Context Documents?

Context documents are files that provide AI agents with the knowledge they need to understand and work with your codebase effectively. They serve as:

- **Project memory**: Architecture, patterns, decisions
- **Coding principles**: Conventions, standards, rules
- **Domain knowledge**: Business logic, relationships, workflows
- **Navigation guide**: Where things are, how they're organized

### Why They're Critical

**Without context documents:**
- AI agents make generic suggestions
- Code doesn't follow your patterns
- Inconsistent architecture decisions
- Repeated explanations of the same concepts

**With good context documents:**
- AI agents understand your architecture
- Code follows established patterns automatically
- Consistent decisions across the codebase
- Self-documenting development process

---

## Types of Context Documents

### Main Context Files

| File | Agent | Location | Purpose |
|------|-------|----------|---------|
| `.cursorrules` | Cursor | Project root | Cursor-specific rules and patterns |
| `CLAUDE.md` | Claude | Project root | Comprehensive project context |
| `STARSHARE.md` | Any | Project root | Project-specific context (example) |
| `.windsurf/` | Windsurf | Project root | Windsurf configuration |

### Supporting Documentation

| Directory | Purpose | When to Use |
|-----------|---------|-------------|
| `docs/patterns/` | Reusable patterns | Pattern used in 2+ places |
| `docs/features/` | Feature specifications | Planning/implementing features |
| `docs/README.md` | Documentation index | Navigation hub |
| `docs/QUICK_REFERENCE.md` | Quick lookup | Human-readable reference |

---

## Core Principles

### 1. Progressive Disclosure

**Principle**: Keep main context file concise, link to detailed docs.

**Structure**:
```
CLAUDE.md (400 lines)
  ├── Overview
  ├── Critical Rules
  ├── Key Patterns (summary)
  └── Links to detailed docs
      ├── docs/patterns/QUERY_CACHE_MANAGEMENT.md
      ├── docs/patterns/ERROR_HANDLING.md
      └── docs/features/PLANS_FEATURE.md
```

**Why**: 
- AI agents can quickly scan main file
- Detailed docs provide comprehensive examples
- Easier to maintain and update

**Example from Starshare**:
```markdown
## TanStack Query Patterns

> **📖 Detailed Documentation**: See [Query Cache Management](docs/patterns/QUERY_CACHE_MANAGEMENT.md)

### Query Keys Convention (Summary)
[Brief example here]
```

### 2. One Source of Truth

**Principle**: Don't duplicate information across files.

**Do**:
- ✅ Reference other docs with links
- ✅ Summarize in main file, detail in pattern docs
- ✅ Update one place, link everywhere

**Don't**:
- ❌ Copy same example to multiple files
- ❌ Duplicate pattern descriptions
- ❌ Maintain same info in multiple places

### 3. Living Documents

**Principle**: Update context documents as code evolves.

**When to update**:
- ✅ New patterns emerge
- ✅ Architecture decisions change
- ✅ New features are added
- ✅ Bugs reveal missing patterns

**Update workflow**:
1. Code changes → Pattern emerges
2. Document pattern in `docs/patterns/`
3. Update main context file with link
4. Update "Last Updated" date

### 4. Prioritize Critical Information

**Principle**: Most important information first.

**Order in main context file**:
1. **Security rules** (CRITICAL - must be first)
2. **Core patterns** (used everywhere)
3. **Architecture** (project structure)
4. **Domain knowledge** (business logic)
5. **Conventions** (naming, formatting)

**Example structure**:
```markdown
# Project Context

## CRITICAL: Security Rules
[Security patterns first]

## Core Patterns
[Most-used patterns]

## Architecture
[Project structure]

## Domain Model
[Business logic]
```

### 5. Code Examples Over Descriptions

**Principle**: Show, don't just tell.

**Do**:
```markdown
### TanStack Query Pattern
```typescript
export const queryKey = 'tasks-list'
export const tasksQueryOptions = (params?) => queryOptions({
  queryKey: [queryKey, params],
  queryFn: () => getTaskPages(params),
})
```
```

**Don't**:
```markdown
### TanStack Query Pattern
Use queryOptions with queryKey and queryFn. Include params in queryKey.
```

---

## Structure of Main Context File

### Recommended Structure

```markdown
# [Project Name] - AI Assistant Context

> **⚠️ MAINTENANCE**: Keep under **20KB** (~400 lines). 
> Move details to `docs/patterns/`. 
> Prioritize: security > patterns > structure.

## Project

| Component | Path | Stack |
|-----------|------|-------|
| Frontend | `/path/to/frontend` | React + TypeScript |
| Backend | `/path/to/backend` | Node.js + Express |

---

## CRITICAL: Security Rules

[Security patterns - MUST be first]

---

## Core Patterns

[Most-used patterns with brief examples]

> **📖 Detailed Documentation**: See [Pattern Name](docs/patterns/PATTERN.md)

---

## Architecture

[Project structure, folder organization]

---

## Domain Model

[Business logic, relationships, workflows]

---

## API Conventions

[API patterns, endpoints, data formats]

---

## Key Features

| Feature | Route | Location |
|---------|-------|----------|
| Feature 1 | `/route` | `src/features/feature1/` |

---

## Documentation

- **Patterns**: `docs/patterns/` (N docs)
- **Index**: `docs/README.md`
- **Quick Reference**: `docs/QUICK_REFERENCE.md`

---

**Version**: X.X | **Updated**: YYYY-MM-DD
```

### Section Guidelines

#### 1. Project Overview

**Purpose**: Quick reference for project structure.

**Include**:
- Component paths (frontend, backend, etc.)
- Tech stack summary
- Key directories

**Example**:
```markdown
## Project

| Component | Path | Stack |
|-----------|------|-------|
| Frontend | `/Users/kibong/development/starshare-app` | React 19 + TanStack + Zustand + Zod |
| Backend | `/Users/kibong/development/starshare` | Rust + Loco.rs + SeaORM + PostgreSQL |
```

#### 2. Security Rules (CRITICAL)

**Purpose**: Prevent security vulnerabilities.

**Include**:
- Authentication patterns
- Authorization rules
- Data validation requirements
- Security anti-patterns

**Example**:
```markdown
## CRITICAL: Security Rules

### Multi-Tenant
**❌ NEVER send `company_id` from frontend** - Backend extracts from JWT.

### Authentication
- NEVER use localStorage for tokens (XSS vulnerability)
- Tokens in HTTP-only cookies only
- API client: `credentials: 'include'`
```

#### 3. Core Patterns

**Purpose**: Most-used patterns with brief examples.

**Include**:
- Pattern name and purpose
- Brief code example
- Link to detailed doc

**Example**:
```markdown
## Frontend Patterns

### TanStack Query
```typescript
export const queryKey = 'tasks-list'
export const tasksQueryOptions = (params?) => queryOptions({
  queryKey: [queryKey, params],
  queryFn: () => getTaskPages(params),
  select: (data) => toCamel<TaskPageResponse>(data),
})
```

**Cache Invalidation**: Match query keys exactly. 
See `docs/patterns/QUERY_CACHE_MANAGEMENT.md`.
```

#### 4. Architecture

**Purpose**: Project structure and organization.

**Include**:
- Folder structure
- Naming conventions
- File organization patterns

**Example**:
```markdown
## Structure

- **Frontend**: `src/features/{name}/` (api/, components/, data/, hooks/) + `src/shared/`
- **Backend**: `src/controllers/` (thin), `src/services/` (fat), `src/models/_entities/`
- **Naming**: Frontend `kebab-case.tsx`, Backend `snake_case.rs`
```

#### 5. Domain Model

**Purpose**: Business logic and relationships.

**Include**:
- Entity relationships
- Key workflows
- Business rules

**Example**:
```markdown
## Domain Relationships

- User ↔ Member: One-to-many (multi-company)
- Member ↔ Brand: Many-to-many via `assignments` (manager/doer)
- Task → Campaign: Many-to-many via `task_campaigns`
- Task → Plan: Many-to-one
```

---

## Writing Pattern Documentation

### When to Create Pattern Docs

**Create pattern doc when**:
- ✅ Solution used successfully in 2+ places
- ✅ Solves a recurring problem
- ✅ Has clear do's and don'ts
- ✅ Would benefit other developers
- ✅ Pattern is stable

**Don't create pattern docs for**:
- ❌ One-off solutions
- ❌ Experimental approaches
- ❌ Feature-specific implementations

### Pattern Document Template

```markdown
# [Pattern Name]

**Date:** YYYY-MM-DD
**Status:** ✅ Implemented | 🚧 In Progress | 📋 Planned

## Overview

Brief description of what this pattern solves.

## Core Principles

1. **Principle 1** - Clear statement
2. **Principle 2** - Clear statement

---

## The Problem

Describe the problem this pattern solves.

### ❌ Anti-Pattern: [Description]

```typescript
// Bad code example showing the problem
```

**Problems**:
- Issue 1
- Issue 2

---

## Solution Patterns

### Pattern 1: [Name]

Description of the pattern.

```typescript
// ✅ CORRECT: Good code example
```

**Benefits**:
- Benefit 1
- Benefit 2

---

## Real-World Example

Show actual implementation from codebase.

```typescript
// src/features/task/api/queries.ts
```

**Key Points**:
- Point 1
- Point 2

---

## Common Pitfalls

### Pitfall 1: [Description]
**Symptom**: What developers observe
**Cause**: Why it happens
**Solution**: How to fix it

---

## Related Patterns

- **Pattern Name**: See `docs/patterns/PATTERN_NAME.md`
- **Feature**: See `docs/features/FEATURE_NAME.md`

## Related Files

**Frontend**:
- `src/path/to/file.ts` - Description

**Backend**:
- `src/path/to/file.rs` - Description

---

**Maintainers:** [Team Name]
**Last Updated:** YYYY-MM-DD
```

---

## Agent-Specific Considerations

### Cursor (.cursorrules)

**Format**: Plain text or markdown

**Key sections**:
- Project overview
- Coding standards
- File structure
- Patterns and conventions

**Example**:
```
# Cursor Rules for [Project Name]

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js + Express

## Patterns
- Use feature-based folder structure
- Follow RESTful API conventions
- Always validate with Zod schemas

## Rules
- Never use `any` type
- Always handle errors
- Use TypeScript strict mode
```

### Claude (CLAUDE.md)

**Format**: Markdown

**Key sections**:
- Same as main context file structure
- More detailed than .cursorrules
- Links to pattern docs

**Example**: See Starshare's `CLAUDE.md` or `STARSHARE.md`

### Windsurf

**Format**: Configuration files in `.windsurf/`

**Key sections**:
- Project settings
- AI model preferences
- Workflow configurations

---

## Maintenance Workflow

### When Code Changes

**AI Agent Workflow**:

1. **Identify affected docs**:
   - Did I create a new pattern?
   - Did I fix a bug worth documenting?
   - Did I change an existing pattern?

2. **Update pattern docs**:
   - If pattern changed: Update pattern doc + "Last Updated" date
   - If new pattern emerged: Create new pattern doc
   - If pattern deprecated: Move to archive

3. **Update main context file**:
   - Add link to new pattern docs
   - Update examples if pattern changed
   - Update "Last Updated" date

4. **Update documentation index**:
   - Add new pattern to navigation
   - Update directory descriptions

### Regular Maintenance

**Weekly**:
- Update "Recently Completed" in main context file
- Move completed items to `docs/completed/`

**Monthly**:
- Review "Last Updated" dates on pattern docs
- Archive obsolete planning docs
- Check for duplicated content

**Quarterly**:
- Review entire docs structure
- Identify missing patterns
- Update templates if needed

---

## Common Mistakes

### ❌ Mistake 1: Too Much Detail in Main File

**Problem**: Main context file becomes 1000+ lines, hard to scan.

**Solution**: Keep main file ~400 lines, move details to pattern docs.

### ❌ Mistake 2: Duplicated Information

**Problem**: Same pattern described in multiple places.

**Solution**: One source of truth, link everywhere else.

### ❌ Mistake 3: Outdated Documentation

**Problem**: Context docs don't match current code.

**Solution**: Update docs as code changes, set reminders for reviews.

### ❌ Mistake 4: Missing Security Rules

**Problem**: Security patterns not documented, AI agents make mistakes.

**Solution**: Always include security rules first in main context file.

### ❌ Mistake 5: Vague Descriptions

**Problem**: "Use this pattern" without examples.

**Solution**: Always include code examples, show don't tell.

---

## Real-World Example: Starshare

The Starshare project demonstrates excellent context document structure:

**Main file**: `STARSHARE.md` (~400 lines)
- Security rules first
- Core patterns with examples
- Links to detailed docs

**Pattern docs**: `docs/patterns/*.md` (21+ docs)
- Comprehensive examples
- Real-world implementations
- Common pitfalls

**Documentation index**: `docs/README.md`
- Navigation hub
- Quick reference
- Learning journey

**Study these files** to see effective context documentation in practice.

---

## Quick Checklist

Before considering your context documents complete:

- [ ] Main context file is ~400 lines or less
- [ ] Security rules are first and prominent
- [ ] Core patterns have code examples
- [ ] Links to detailed pattern docs
- [ ] "Last Updated" date is current
- [ ] No duplicated information
- [ ] Pattern docs follow template
- [ ] Documentation index is up-to-date
- [ ] Real-world examples included
- [ ] Common pitfalls documented

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Study Starshare's context documents
3. → [Starting from Scratch](../scenarios/starting-from-scratch.md) or [Migrating Existing Projects](../scenarios/migrating-existing-projects.md)
4. → Create your first context document
5. → Iterate and improve based on agent feedback

---

**Questions?** See [Troubleshooting](../advanced/troubleshooting.md) or study the Starshare project examples.

