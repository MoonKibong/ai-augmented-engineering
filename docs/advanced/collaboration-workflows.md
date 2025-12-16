# Collaboration Workflows with AI Agents

> **Purpose**: Guide for working with AI agents in team environments and maintaining consistency.

**Last Updated**: 2025-12-15 
**Audience**: Teams using AI agents for development

---

## Overview

Using AI agents in team environments requires:
- Consistent context documents across team
- Code review processes that include AI-generated code
- Version control best practices
- Team communication about patterns and decisions

**This guide covers**:
1. Team context document management
2. Code review with AI assistance
3. Maintaining consistency
4. Version control workflows
5. Team communication

---

## Team Context Documents

### Shared Context Files

**All team members should use the same context documents**:
- `.cursorrules` (for Cursor users)
- `CLAUDE.md` (for Claude users)
- `docs/patterns/*.md` (shared patterns)
- `docs/README.md` (documentation index)

### Version Control

**Commit context documents to Git**:
```bash
git add .cursorrules CLAUDE.md docs/
git commit -m "docs: update context documents"
```

**Why**:
- ✅ Everyone has same context
- ✅ Changes are tracked
- ✅ Easy to review updates
- ✅ New team members get context automatically

### Updating Context Documents

**Workflow**:
1. **Team member** identifies need to update
2. **Create PR** with context document changes
3. **Team reviews** the changes
4. **Merge** after approval
5. **All team members** pull updates

**Example PR**:
```markdown
## Update Context Documents

### Changes
- Added new query pattern
- Updated error handling pattern
- Fixed security rule documentation

### Why
- New pattern emerged from recent work
- Error handling pattern was incomplete
- Security rules needed clarification
```

---

## Code Review with AI Agents

### Reviewing AI-Generated Code

**Standard review process applies**:
- ✅ Check functionality
- ✅ Verify it follows patterns
- ✅ Test edge cases
- ✅ Check for security issues
- ✅ Verify documentation

**Additional considerations**:
- ✅ Does it follow documented patterns?
- ✅ Are there new patterns that should be documented?
- ✅ Is the code consistent with existing codebase?

### AI-Assisted Code Review

**Use AI agents to help review**:
```
Prompt: "Review this PR for:
1. Does it follow our documented patterns?
2. Are there any issues?
3. Are there improvements needed?
4. Should any patterns be documented?"
```

**Benefits**:
- Consistent pattern checking
- Catches common issues
- Suggests improvements
- Identifies missing documentation

### Review Checklist

**For AI-generated code**:
- [ ] Follows documented patterns
- [ ] No security issues
- [ ] Error handling is appropriate
- [ ] Tests are included (if applicable)
- [ ] Documentation is updated (if needed)
- [ ] Code is consistent with codebase

---

## Maintaining Consistency

### Pattern Enforcement

**Document patterns clearly**:
- ✅ Clear examples in pattern docs
- ✅ Anti-patterns documented
- ✅ Common pitfalls explained

**Use AI agents to enforce**:
- ✅ Reference patterns in prompts
- ✅ Ask AI to follow specific patterns
- ✅ Review generated code against patterns

### Code Style Consistency

**Establish style guide**:
- Document in context files
- Use linters and formatters
- Configure AI agents to follow style

**Example**:
```markdown
## Code Style

- Use TypeScript strict mode
- Prefer functional components
- Use named exports
- Follow ESLint rules
```

### Architecture Consistency

**Document architecture decisions**:
- Folder structure
- Naming conventions
- Design patterns
- Technology choices

**Enforce through context**:
- ✅ Clear architecture documentation
- ✅ Examples of correct structure
- ✅ Anti-patterns to avoid

---

## Version Control Workflows

### Commit Messages

**Include context in commits**:
```bash
git commit -m "feat: add user profile feature

- Follows our feature-based structure
- Uses React Query pattern
- Includes error handling
- Updates documentation"
```

**Why**:
- Shows pattern awareness
- Helps reviewers understand approach
- Documents decisions

### Branch Strategy

**Standard Git workflow applies**:
- Feature branches
- PR reviews
- Merge to main

**Considerations**:
- ✅ Update context docs in same PR if patterns change
- ✅ Document new patterns before merging
- ✅ Update documentation index if needed

### Handling Conflicts

**Context document conflicts**:
- Usually easy to resolve (text files)
- Review both versions
- Merge changes appropriately
- Update "Last Updated" dates

**Code conflicts**:
- Standard Git conflict resolution
- Use AI agents to help understand changes
- Verify patterns are maintained

---

## Team Communication

### Pattern Discussions

**When to discuss patterns**:
- New pattern emerges
- Pattern needs clarification
- Pattern should be changed
- Inconsistency discovered

**Communication channels**:
- PR comments
- Team meetings
- Documentation updates
- Slack/chat discussions

### Documentation Updates

**Notify team of updates**:
- PR description for context doc changes
- Team chat for important pattern updates
- Documentation in PR comments

**Example**:
```markdown
## Context Document Update

Updated query pattern to include new cache invalidation approach.
All team members should review and update their local context.
```

### Onboarding New Team Members

**Process**:
1. **Share context documents**:
   - `.cursorrules` or `CLAUDE.md`
   - `docs/README.md`
   - Pattern documentation

2. **Explain workflow**:
   - How to use AI agents
   - How to update context documents
   - Code review process

3. **Provide examples**:
   - Show example prompts
   - Demonstrate workflows
   - Review pattern docs together

---

## Best Practices

### Team Context Management

**Do**:
- ✅ Keep context documents in version control
- ✅ Review context updates in PRs
- ✅ Update as patterns evolve
- ✅ Communicate important changes

**Don't**:
- ❌ Have different context per team member
- ❌ Skip reviewing context updates
- ❌ Let context documents get outdated
- ❌ Make breaking changes without discussion

### Code Review

**Do**:
- ✅ Review AI-generated code thoroughly
- ✅ Check pattern compliance
- ✅ Verify documentation updates
- ✅ Test functionality

**Don't**:
- ❌ Assume AI-generated code is perfect
- ❌ Skip pattern checks
- ❌ Ignore documentation needs
- ❌ Accept without testing

### Pattern Evolution

**Do**:
- ✅ Document patterns as they emerge
- ✅ Discuss pattern changes with team
- ✅ Update context documents
- ✅ Refactor gradually

**Don't**:
- ❌ Change patterns without discussion
- ❌ Skip documentation
- ❌ Break existing code unnecessarily
- ❌ Create inconsistencies

---

## Common Scenarios

### Scenario 1: New Pattern Emerges

**Situation**: Team member discovers new pattern

**Process**:
1. Document pattern in PR
2. Team reviews and discusses
3. Create pattern doc if approved
4. Update context documents
5. Refactor existing code gradually

### Scenario 2: Pattern Inconsistency

**Situation**: Same functionality implemented differently

**Process**:
1. Identify all variations
2. Discuss with team
3. Choose standard approach
4. Document standard pattern
5. Plan migration

### Scenario 3: Context Document Conflict

**Situation**: Multiple team members update context simultaneously

**Process**:
1. Review both versions
2. Merge changes appropriately
3. Resolve conflicts
4. Verify consistency
5. Update dates

---

## Tools and Automation

### Pre-commit Hooks

**Check context documents**:
- Verify format
- Check links
- Validate structure

**Example**:
```bash
#!/bin/bash
# Check context document format
if ! grep -q "Last Updated" CLAUDE.md; then
  echo "Error: CLAUDE.md missing 'Last Updated' date"
  exit 1
fi
```

### CI/CD Checks

**Validate documentation**:
- Check for broken links
- Verify pattern doc structure
- Check context document format

### Documentation Linters

**Use tools to check**:
- Markdown linting
- Link checking
- Structure validation

---

## Troubleshooting

### Issue: Team members have different context

**Solution**:
- Ensure context documents are in version control
- Require PR reviews for context updates
- Communicate updates clearly

### Issue: Patterns not being followed

**Solution**:
- Review pattern documentation clarity
- Provide more examples
- Use AI agents to enforce patterns
- Code review for pattern compliance

### Issue: Documentation conflicts

**Solution**:
- Use clear merge strategies
- Review both versions carefully
- Communicate about updates
- Update dates appropriately

---

## Checklist: Team Collaboration

### Setup
- [ ] Context documents in version control
- [ ] All team members have access
- [ ] Documentation structure established
- [ ] Review process defined

### Ongoing
- [ ] Context documents updated regularly
- [ ] Pattern changes discussed with team
- [ ] Code reviews include pattern checks
- [ ] Documentation stays current
- [ ] Team communication is clear

### Onboarding
- [ ] New members get context documents
- [ ] Workflow is explained
- [ ] Examples are provided
- [ ] Questions are answered

---

## Next Steps

1. ✅ Read this guide (you're here!)
2. → Set up team context document workflow
3. → Establish code review process
4. → Communicate patterns with team
5. → Iterate and improve

---

## Resources

- **Context Documents**: [Writing Effective Context Documents](../context-documents/README.md)
- **Documentation Patterns**: [Documentation Patterns](./documentation-patterns.md)
- **Getting Started**: [Getting Started Guide](../getting-started/README.md)

---

**Ready to collaborate?** Set up your team workflow and start!

