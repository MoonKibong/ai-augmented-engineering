# Migrating Existing Projects to AI Agents

> **Purpose**: Step-by-step guide for onboarding AI agents to existing codebases and gradually improving collaboration.

**Last Updated**: 2025-12-15
**Audience**: Developers with existing projects

---

## Overview

Migrating an existing project to use AI agents involves:
- Analyzing current architecture and patterns
- Creating context documents from existing code
- Gradually improving documentation
- Establishing patterns that may be implicit

**This guide covers**:
1. Analyzing your existing codebase
2. Creating initial context documents
3. Documenting existing patterns
4. Gradual adoption strategies
5. Handling legacy code and technical debt

---

## Prerequisites

Before starting:
- ✅ Read [Getting Started Guide](../getting-started/README.md)
- ✅ Read [Writing Effective Context Documents](../context-documents/README.md)
- ✅ Have access to your existing codebase
- ✅ Understand your project's current structure

---

## Phase 1: Codebase Analysis

### Step 1: Understand Current Structure

**With AI Agent**:
```
Prompt: "Analyze this codebase and help me understand:
1. What's the overall architecture?
2. How is code organized?
3. What patterns are being used?
4. What are the key components?"
```

**Manual analysis**:
- Review folder structure
- Identify main entry points
- Understand dependencies
- Note any documentation that exists

**Create analysis document**:
```markdown
# Codebase Analysis

## Architecture
[Your findings]

## Structure
[Folder organization]

## Patterns Identified
[Patterns you notice]

## Key Components
[Important files/modules]
```

### Step 2: Identify Existing Patterns

**Look for**:
- Repeated code structures
- Common error handling approaches
- Data fetching patterns
- State management patterns
- Component patterns

**With AI Agent**:
```
Prompt: "Review these files [list files] and identify:
1. What patterns are being used?
2. Are there inconsistencies?
3. What patterns should be standardized?"
```

**Document findings**:
- List patterns you've identified
- Note inconsistencies
- Prioritize which patterns to document first

### Step 3: Identify Technical Debt

**Look for**:
- Inconsistent patterns
- Outdated approaches
- Missing documentation
- Code that needs refactoring

**Document**:
- What needs to be fixed
- What can be improved
- What should be documented

---

## Phase 2: Create Initial Context Documents

### Step 1: Create Basic Context File

**Start with essentials**:

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

[Document security patterns from existing code]

---

## Architecture

[Document current structure - even if imperfect]

---

## Current Patterns

[Document patterns as you identify them]

---

**Version**: 0.1 | **Updated**: YYYY-MM-DD
```

### Step 2: Document Current Architecture

**With AI Agent**:
```
Prompt: "Based on this codebase structure, help me document:
1. How files are organized
2. What the main components are
3. How data flows through the system
4. Key architectural decisions (even if implicit)"
```

**Include**:
- Folder structure (even if not ideal)
- Main entry points
- Key modules/components
- Data flow

**Example**:
```markdown
## Architecture

### Current Structure
- `src/components/` - React components
- `src/services/` - API calls
- `src/utils/` - Utility functions
- `src/store/` - Redux store

### Key Components
- `App.tsx` - Main application component
- `api.ts` - API client
- `store.ts` - Redux store configuration
```

### Step 3: Document Existing Patterns

**Start with most-used patterns**:

**With AI Agent**:
```
Prompt: "I've identified that we use [pattern] in multiple places. 
Help me document this pattern:
1. What problem does it solve?
2. Show examples from the codebase
3. What are the variations?
4. What should be standardized?"
```

**Create pattern doc**:
- Use pattern template
- Include real examples from codebase
- Note inconsistencies
- Document what should be standardized

---

## Phase 3: Gradual Documentation

### Strategy: Document as You Work

**Don't try to document everything at once!**

**Instead**:
1. **Document as you work**: When you touch code, document it
2. **Prioritize active areas**: Document code you're actively changing
3. **Fix and document**: When refactoring, document the new pattern
4. **Incremental improvement**: Each session, improve documentation

### Workflow: Document While Coding

1. **Start work on feature/area**
2. **Review existing code** in that area
3. **Identify patterns** being used
4. **Document patterns** if not already documented
5. **Make improvements** if patterns are inconsistent
6. **Update context** with new patterns

### Example: Documenting API Patterns

**Scenario**: Working on a new API endpoint

**Steps**:
1. **Review existing API code**:
   ```
   Prompt: "Review our existing API endpoints and identify the pattern."
   ```

2. **Document the pattern**:
   ```
   Prompt: "Create a pattern document for our API endpoint structure 
   based on these examples [list files]."
   ```

3. **Follow pattern for new code**:
   ```
   Prompt: "Create a new API endpoint following our documented pattern."
   ```

4. **Update context file**:
   - Add link to API pattern doc
   - Update if pattern improved

---

## Phase 4: Standardizing Patterns

### Identify Inconsistencies

**With AI Agent**:
```
Prompt: "Compare these files [list similar files] and identify:
1. What patterns are consistent?
2. What's inconsistent?
3. What should be standardized?
4. What's the recommended approach?"
```

### Create Standard Pattern

**When you find inconsistencies**:

1. **Analyze variations**:
   - What are the different approaches?
   - Which is best?
   - What should be standard?

2. **Document standard**:
   ```
   Prompt: "Based on these examples, create a standardized pattern document 
   that we should follow going forward."
   ```

3. **Plan migration** (if needed):
   - Can we migrate gradually?
   - Do we need to migrate all at once?
   - What's the priority?

### Refactor Gradually

**Don't refactor everything at once!**

**Strategy**:
- **Refactor when touching code**: If you're already working on a file, refactor it
- **Prioritize high-impact**: Focus on code that's changed frequently
- **Document as you go**: Update docs as you refactor

**With AI Agent**:
```
Prompt: "Refactor this file [file path] to follow our documented pattern 
[pattern name]. Make sure it maintains the same functionality."
```

---

## Phase 5: Handling Legacy Code

### Document Legacy Patterns

**Even if you plan to replace them**:

```markdown
## Legacy Patterns (To Be Replaced)

### Old Pattern: [Name]
**Status**: ⚠️ Legacy - Do not use in new code
**Replacement**: [New pattern name]

[Document old pattern for reference]
```

**Why document legacy code?**
- AI agents need to understand existing code
- Helps with gradual migration
- Prevents accidental use of old patterns

### Gradual Migration Strategy

**Option 1: Strangler Pattern**
- New code uses new patterns
- Old code remains until replaced
- Document both patterns

**Option 2: Refactor on Touch**
- When you work on legacy code, refactor it
- Document new pattern
- Update context

**Option 3: Big Bang Refactor**
- Refactor entire area at once
- Document new pattern
- Update all references

**Recommendation**: Option 2 (refactor on touch) is usually best.

### Working with Legacy Code

**When you must work with legacy code**:

1. **Document what it does**:
   ```
   Prompt: "Help me understand what this legacy code does and document it."
   ```

2. **Identify dependencies**:
   ```
   Prompt: "What other code depends on this legacy code?"
   ```

3. **Plan refactoring** (if needed):
   ```
   Prompt: "Help me plan how to refactor this legacy code to use our new patterns."
   ```

---

## Phase 6: Establishing New Patterns

### When to Create New Patterns

**Create new patterns when**:
- ✅ You're adding new functionality
- ✅ You're refactoring legacy code
- ✅ You're standardizing inconsistencies
- ✅ You're adopting new libraries/approaches

### Pattern Creation Workflow

1. **Use pattern in 2+ places**:
   - Try it in first location
   - Use it in second location
   - Refine if needed

2. **Document the pattern**:
   ```
   Prompt: "I've used [pattern] in multiple places. Create a pattern document 
   following our template."
   ```

3. **Update context file**:
   - Add to main context file
   - Link to pattern doc

4. **Refactor existing code** (if needed):
   - Gradually migrate to new pattern
   - Update as you touch code

---

## Common Scenarios

### Scenario 1: Undocumented Codebase

**Situation**: Large codebase with no documentation

**Approach**:
1. Create basic context file with structure
2. Document patterns as you work on them
3. Use AI agent to analyze and document
4. Gradually build up documentation

**With AI Agent**:
```
Prompt: "This is a large, undocumented codebase. Help me create an initial 
context document by analyzing the structure and key files."
```

### Scenario 2: Inconsistent Patterns

**Situation**: Same functionality implemented differently in multiple places

**Approach**:
1. Identify all variations
2. Choose best approach (or create new one)
3. Document standard pattern
4. Migrate gradually

**With AI Agent**:
```
Prompt: "I have inconsistent implementations of [functionality]. 
Help me create a standardized pattern and plan the migration."
```

### Scenario 3: Outdated Patterns

**Situation**: Code uses old patterns that should be updated

**Approach**:
1. Document current (old) pattern
2. Create new pattern
3. Mark old pattern as legacy
4. Migrate gradually

**With AI Agent**:
```
Prompt: "This code uses an outdated pattern. Help me create a modern 
replacement pattern and plan the migration."
```

### Scenario 4: Mixed Tech Stacks

**Situation**: Codebase uses multiple approaches (e.g., class components + hooks)

**Approach**:
1. Document both approaches
2. Choose standard for new code
3. Mark old approach as legacy
4. Migrate gradually

**With AI Agent**:
```
Prompt: "Our codebase mixes [old approach] and [new approach]. 
Help me document both and establish a standard for new code."
```

---

## Pitfalls to Avoid

### ❌ Pitfall 1: Trying to Document Everything at Once

**Problem**: Overwhelming, never finishes, gets outdated

**Solution**: Document incrementally as you work

### ❌ Pitfall 2: Ignoring Legacy Code

**Problem**: AI agents don't understand legacy patterns

**Solution**: Document legacy patterns, even if planning to replace

### ❌ Pitfall 3: Not Standardizing Inconsistencies

**Problem**: Documentation doesn't match reality

**Solution**: Document current state, then standardize gradually

### ❌ Pitfall 4: Perfect Documentation

**Problem**: Waiting for perfect docs before using AI agents

**Solution**: Start with basic docs, improve iteratively

### ❌ Pitfall 5: Not Updating Documentation

**Problem**: Docs become outdated as code changes

**Solution**: Update docs as you change code, set reminders

---

## Real-World Example: Starshare Migration

The Starshare project demonstrates effective migration:

**Initial state**:
- Existing React + Rust codebase
- Some patterns, not all documented
- Mixed approaches in some areas

**Migration approach**:
1. Created `STARSHARE.md` with current architecture
2. Documented patterns as they were identified
3. Standardized inconsistencies gradually
4. Created pattern docs as patterns emerged
5. Maintained documentation as code evolved

**Result**:
- 21+ documented patterns
- Comprehensive context document
- Living documentation that stays current
- Effective AI agent collaboration

**Study Starshare's documentation** to see migration in practice.

---

## Checklist: Migrating Existing Project

### Initial Analysis
- [ ] Codebase structure analyzed
- [ ] Existing patterns identified
- [ ] Technical debt documented
- [ ] Key components understood

### Context Documents
- [ ] Basic context file created
- [ ] Current architecture documented
- [ ] Existing patterns documented
- [ ] Documentation structure created

### Gradual Documentation
- [ ] Strategy for incremental docs established
- [ ] Workflow for documenting while coding
- [ ] Pattern documentation template ready

### Standardization
- [ ] Inconsistencies identified
- [ ] Standard patterns established
- [ ] Migration plan created (if needed)

### Legacy Code
- [ ] Legacy patterns documented
- [ ] Migration strategy decided
- [ ] New patterns established

### Ongoing
- [ ] Documentation updated as code changes
- [ ] Patterns refined based on experience
- [ ] Context documents stay current

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Analyze your codebase
3. → Create initial context documents
4. → Start documenting patterns as you work
5. → Reference [Agent-Specific Guides](../agents/cursor.md) as needed
6. → See [Advanced Topics](../advanced/documentation-patterns.md) for more

---

## Resources

- **Context Documents Guide**: [Writing Effective Context Documents](../context-documents/README.md)
- **Real-World Example**: Study Starshare project documentation
- **Agent Guides**: [Cursor](../agents/cursor.md), [Claude](../agents/claude.md), [Windsurf](../agents/windsurf.md)

---

**Ready to start?** Begin with Phase 1: Codebase Analysis!

