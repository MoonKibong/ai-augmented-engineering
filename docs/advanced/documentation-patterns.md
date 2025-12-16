# Documentation Patterns for AI Agents

> **Purpose**: Advanced guide on structuring and maintaining documentation that works effectively with AI agents.

**Last Updated**: 2025-12-15
**Audience**: Developers maintaining documentation for AI agent collaboration

---

## Overview

Effective documentation for AI agents requires specific patterns and structures. This guide covers:
- Documentation hierarchy and organization
- Pattern documentation vs feature documentation
- Maintaining living documentation
- Documentation workflows for AI agents

**Based on**: Real-world patterns from the Starshare project

---

## Documentation Hierarchy

### Three-Tier Structure

```
Tier 1: Main Context File (CLAUDE.md, .cursorrules)
  ├── ~400 lines
  ├── High-level overview
  ├── Critical rules
  └── Links to detailed docs

Tier 2: Pattern Documentation (docs/patterns/*.md)
  ├── Comprehensive patterns
  ├── Real-world examples
  ├── Common pitfalls
  └── Related patterns

Tier 3: Feature Documentation (docs/features/*.md)
  ├── Feature specifications
  ├── Implementation details
  ├── User flows
  └── API references
```

### Why This Structure?

**Progressive Disclosure**:
- AI agents can quickly scan main file
- Detailed docs provide comprehensive examples
- Easier to maintain and update

**One Source of Truth**:
- Main file references, doesn't duplicate
- Pattern docs are authoritative
- Feature docs are specific

**Scalability**:
- Main file stays manageable
- Pattern docs can be comprehensive
- Easy to add new docs

---

## Pattern Documentation

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

### Pattern Documentation Best Practices

**Include code examples**:
- ✅ Show both wrong and right
- ✅ Use real code from codebase
- ✅ Include file paths

**Document common pitfalls**:
- ✅ What goes wrong
- ✅ Why it happens
- ✅ How to fix it

**Link to related patterns**:
- ✅ Show relationships
- ✅ Help navigation
- ✅ Build knowledge graph

---

## Feature Documentation

### When to Create Feature Docs

**Create feature doc when**:
- ✅ Planning a new feature
- ✅ Feature is complex
- ✅ Multiple components involved
- ✅ Needs specification

**Don't create feature docs for**:
- ❌ Simple features
- ❌ One-component features
- ❌ Features that follow standard patterns

### Feature Document Template

```markdown
# [Feature Name]

**Date:** YYYY-MM-DD
**Status:** ✅ Implemented | 🚧 In Progress | 📋 Planned
**Route:** `/feature-route`

## Overview

Brief description of the feature.

## User Stories

- As a [user], I want [goal] so that [benefit]

## UI/UX Design

[Describe or link to designs]

## Component Hierarchy

```
FeatureComponent
├── SubComponent1
├── SubComponent2
└── SubComponent3
```

## State Management

[Describe state management approach]

## API Endpoints

| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/api/endpoint` | Description |
| POST | `/api/endpoint` | Description |

## Implementation Details

[Technical details]

## Related Patterns

- **Pattern Name**: See `docs/patterns/PATTERN_NAME.md`

## Related Files

**Frontend**:
- `src/features/feature-name/` - Feature implementation

**Backend**:
- `src/controllers/feature.rs` - API endpoints

---

**Last Updated:** YYYY-MM-DD
```

---

## Maintaining Living Documentation

### Update Workflows

**When code changes**:

1. **Identify affected docs**:
   - Did I create a new pattern?
   - Did I change an existing pattern?
   - Does main context file need updating?

2. **Update pattern docs**:
   - If pattern changed: Update doc + date
   - If new pattern: Create new doc
   - If pattern deprecated: Archive

3. **Update main context file**:
   - Add link to new pattern docs
   - Update examples if pattern changed
   - Update "Last Updated" date

4. **Update documentation index**:
   - Add new pattern to navigation
   - Update directory descriptions

### Regular Maintenance

**Weekly**:
- Update "Recently Completed" in main context
- Move completed items to `docs/completed/`

**Monthly**:
- Review "Last Updated" dates
- Archive obsolete docs
- Check for duplicated content

**Quarterly**:
- Review entire docs structure
- Identify missing patterns
- Update templates if needed

### AI Agent Responsibilities

**AI agents should**:
- ✅ Update docs when patterns change
- ✅ Create pattern docs when patterns emerge
- ✅ Update "Last Updated" dates
- ✅ Link to related docs
- ✅ Ask before archiving

**AI agents should not**:
- ❌ Duplicate information
- ❌ Create docs without user approval (for new patterns)
- ❌ Assume docs are obsolete
- ❌ Skip documentation updates

---

## Documentation Index

### Purpose

The documentation index (`docs/README.md`) serves as:
- Navigation hub
- Quick reference
- Learning path
- Pattern catalog

### Structure

```markdown
# Project Documentation

## Quick Navigation

| Category | Description | Location |
|----------|-------------|----------|
| Patterns | Established patterns | `patterns/` |
| Features | Feature specs | `features/` |
| API | API reference | `api/` |

## Core Pattern Documentation

### 1. [Pattern Name]
**File**: `docs/patterns/PATTERN_NAME.md`
**Topics**: [Key topics]
**Read this if**: [When to read]

## Features

- [Feature 1](features/FEATURE1.md)
- [Feature 2](features/FEATURE2.md)

## Quick Reference

[Quick lookup items]
```

---

## Cross-Referencing Rules

### In Main Context File

**Pattern**: Summary + link to detailed doc

```markdown
## TanStack Query Patterns

> **📖 Detailed Documentation**: See [Query Cache Management](docs/patterns/QUERY_CACHE_MANAGEMENT.md)

### Query Keys Convention (Summary)
[Brief example here]
```

### In Pattern Docs

**Pattern**: Link to related patterns and files

```markdown
## Related Patterns

- **Query Cache Management**: See `docs/patterns/QUERY_CACHE_MANAGEMENT.md`
- **Error Handling**: See `docs/patterns/ERROR_HANDLING.md`

## Related Files

**Frontend**:
- `src/features/task/api/queries.ts` - Query options implementation
```

---

## Archiving Strategy

### When to Archive

**Archive docs when**:
- ✅ Information is outdated
- ✅ Better documentation exists
- ✅ Pattern is deprecated
- ✅ Experimental approach abandoned

**Don't archive**:
- ❌ Current patterns
- ❌ Active planning docs
- ❌ Recent completed work (6 months minimum)

### Archiving Workflow

1. **Move to archive**:
   ```bash
   mv docs/patterns/OLD_PATTERN.md docs/archive/
   ```

2. **Add deprecation notice**:
   ```markdown
   > **⚠️ DEPRECATED**: This pattern is outdated.
   > See `docs/patterns/NEW_PATTERN.md` for current approach.
   > **Archived**: YYYY-MM-DD
   ```

3. **Update links**:
   - Remove from README.md
   - Update main context file
   - Leave breadcrumbs in related docs

---

## Documentation Consistency

### Before Committing Docs

**Checklist**:
- [ ] Frontmatter includes Date and Status
- [ ] Code examples use ❌ WRONG vs ✅ CORRECT format
- [ ] File paths are accurate
- [ ] Cross-references use correct paths
- [ ] "Last Updated" date is current
- [ ] No duplicated content
- [ ] Markdown formatting is consistent
- [ ] Links are working

### Monthly Review

**AI Agent Prompt**:
```
Review docs/ directory:
1. Check for outdated "Last Updated" dates
2. Identify duplicated content
3. Find broken cross-references
4. Suggest candidates for archiving
5. Identify missing pattern docs
6. Check main context file is up-to-date
```

---

## Real-World Example: Starshare

The Starshare project demonstrates excellent documentation patterns:

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

**Meta-documentation**: `docs/DOCUMENTATION_PATTERNS.md`
- Documentation standards
- Templates and workflows
- Maintenance guidelines

**Study these files** to see effective documentation in practice.

---

## Anti-Patterns

### ❌ Don't Do This

1. **Duplicating content**:
   ```markdown
   ❌ Copy same example to multiple docs
   ✅ Link to canonical doc
   ```

2. **Outdated dates**:
   ```markdown
   ❌ Last Updated: 2024-10-01 (but edited today)
   ✅ Update date when editing
   ```

3. **Vague cross-references**:
   ```markdown
   ❌ "See the cache management doc"
   ✅ See [Query Cache Management](docs/patterns/QUERY_CACHE_MANAGEMENT.md)
   ```

4. **Code without context**:
   ```markdown
   ❌ Just showing code
   ✅ Show problem, then solution, then benefits
   ```

5. **Missing file paths**:
   ```markdown
   ❌ "In the asset component"
   ✅ In `src/features/asset/components/asset-card.tsx`
   ```

---

## Success Metrics

Good documentation should:
- ✅ Enable new developers to contribute without asking basic questions
- ✅ Prevent repeating same bugs/mistakes
- ✅ Make architectural decisions explicit and findable
- ✅ Serve as educational resource
- ✅ Stay up-to-date with code changes
- ✅ Help AI agents understand and follow patterns

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Study Starshare's documentation structure
3. → Apply patterns to your project
4. → Create pattern docs as patterns emerge
5. → Maintain documentation as code evolves

---

## Resources

- **Context Documents**: [Writing Effective Context Documents](../context-documents/README.md)
- **Real-World Example**: Study Starshare project at `/Users/kibong/development/starshare-app`
- **Documentation Patterns**: See Starshare's `docs/DOCUMENTATION_PATTERNS.md`

---

**Questions?** See [Troubleshooting](./troubleshooting.md) or study the Starshare project examples.

