# AI-Augmented Engineering Training Materials

> **Welcome!** 👋 This repository is designed to help developers and software engineers who are new to AI-augmented engineering get started quickly and build a comprehensive understanding of how to use AI agents in their everyday work.

**Last Updated**: 2025-12-15  
**Version**: 1.0

---

## 🎯 Purpose

As an experienced trainer, I've created these materials to bridge the gap between traditional software development and the emerging world of AI-augmented engineering. Whether you're a junior developer or a seasoned engineer, working with AI agents like **Cursor**, **Claude**, and **Windsurf** can dramatically accelerate your productivity—but only if you know how to collaborate with them effectively.

This isn't just about "asking ChatGPT to write code." It's about:
- **Building a partnership** with AI agents that understand your project
- **Establishing patterns** that AI agents can follow consistently
- **Creating living documentation** that serves as the "memory" for AI collaboration
- **Maintaining quality** while moving faster than ever before

Think of AI agents as incredibly skilled junior developers who:
- ✅ Never get tired or frustrated
- ✅ Can instantly recall every line of code in your project
- ✅ Follow documented patterns perfectly (when given clear instructions)
- ❌ But need context, guidance, and review to produce great work

This training will teach you how to provide that context and guidance effectively.

---

## 📚 What's Inside

This repository contains comprehensive training materials covering:

### Core Topics
- **Getting started** with AI agents (setup, first steps, expectations)
- **Writing effective context documents** (the secret to successful AI collaboration)
- **Two main scenarios**: Starting from scratch vs. migrating existing projects
- **Agent-specific guides**: Detailed workflows for Cursor, Claude, and Windsurf
- **Advanced topics**: Documentation patterns, team collaboration, troubleshooting

### Real-World Examples
All materials are based on patterns and practices from the **Starshare** project—a production full-stack application built with AI agent assistance. You'll see real examples, not theoretical concepts.

---

## 🚀 How to Use These Materials

You have **two ways** to explore the content, depending on your learning style:

### Option 1: Reading Path (Comprehensive) 📖

**Start here**: [`docs/README.md`](./docs/README.md)

This is the main documentation hub with a chronological reading order. Follow the numbered sequence:

1. **Getting Started** → Understand what AI agents are and how to set them up
2. **Context Documents** → Learn the most critical skill for AI collaboration
3. **Choose Your Scenario**:
   - Starting a new project? → [`docs/scenarios/starting-from-scratch.md`](./docs/scenarios/starting-from-scratch.md)
   - Have an existing project? → [`docs/scenarios/migrating-existing-projects.md`](./docs/scenarios/migrating-existing-projects.md)
4. **Agent-Specific Guides** → Deep dive into your chosen agent (Cursor, Claude, or Windsurf)
5. **Advanced Topics** → Documentation patterns, collaboration, troubleshooting

**Reading time**: 2-3 hours for core materials, 4-5 hours for everything

### Option 2: Interactive Slides (Quick Start) 🎬

**[View Interactive Slides](https://htmlpreview.github.io/?https://github.com/MoonKibong/ai-augmented-engineering/blob/main/index.html)** → `index.html`

An interactive slide presentation that covers the essentials in a visual, engaging format. Perfect for:
- Team training sessions
- Quick overviews
- Visual learners
- Presentation to stakeholders

**Viewing time**: 30-45 minutes

---

## 📁 Repository Structure

```
agentic-coding/
├── README.md                          # You are here! 👈
├── index.html                         # Interactive slides (view online)
│
├── docs/                              # Complete documentation
│   ├── README.md                      # Main navigation hub ⭐ START HERE
│   │
│   ├── getting-started/
│   │   └── README.md                  # Introduction & first steps
│   │
│   ├── context-documents/
│   │   └── README.md                  # Critical: How to write context docs
│   │
│   ├── scenarios/
│   │   ├── starting-from-scratch.md   # Building new projects
│   │   └── migrating-existing-projects.md  # Onboarding existing code
│   │
│   ├── agents/
│   │   ├── cursor.md                  # Cursor IDE guide
│   │   ├── claude.md                  # Claude Code guide
│   │   └── windsurf.md                # Windsurf IDE guide
│   │
│   └── advanced/
│       ├── documentation-patterns.md  # How to structure docs
│       ├── collaboration-workflows.md # Team collaboration
│       └── troubleshooting.md         # Common issues & solutions
│
└── docs-for-upload/                   # Flattened versions for Gemini/LLM upload
    ├── 00-main-index.md
    ├── 01-getting-started.md
    ├── 02-context-documents-guide.md
    └── ... (all docs with unique names)
```

---

## 🎓 Learning Paths

### Path 1: The Quick Start (1 hour)

**For**: Developers who want to get started immediately

1. Read [`docs/getting-started/README.md`](./docs/getting-started/README.md) (15 min)
2. Read [`docs/context-documents/README.md`](./docs/context-documents/README.md) (20 min)
3. Choose one agent guide:
   - [Cursor](./docs/agents/cursor.md) (15 min)
   - [Claude](./docs/agents/claude.md) (15 min)
   - [Windsurf](./docs/agents/windsurf.md) (15 min)
4. Start experimenting! 🚀

### Path 2: The Comprehensive Course (4-5 hours)

**For**: Developers who want deep understanding

1. Read all of [`docs/README.md`](./docs/README.md) in order (3-4 hours)
2. Study the Starshare project examples referenced throughout (1 hour)
3. Practice with your own projects
4. Reference advanced topics as needed

### Path 3: The Team Training (2-3 hours)

**For**: Teams adopting AI-augmented development

1. Watch interactive slides (`index.html` - coming soon) (45 min)
2. Discuss team workflow and patterns (30 min)
3. Read [`docs/context-documents/README.md`](./docs/context-documents/README.md) together (30 min)
4. Read [`docs/advanced/collaboration-workflows.md`](./docs/advanced/collaboration-workflows.md) (30 min)
5. Set up team context documents (30 min)

---

## 💡 Key Concepts You'll Learn

### 1. Context Documents (Most Critical!)

You'll learn to create files like `CLAUDE.md`, `.cursorrules`, or `AGENTS.md` that serve as the "brain" for AI collaboration. These documents:
- Explain your project's architecture and patterns
- Define coding standards and conventions
- Document security rules and constraints
- Link to detailed pattern documentation

**Without good context documents**, AI agents produce generic, inconsistent code.  
**With good context documents**, AI agents become project experts who follow your patterns automatically.

### 2. Progressive Disclosure

Keep your main context file ~400 lines, linking to detailed pattern documentation. This makes it easy for AI agents to scan quickly while having access to comprehensive examples when needed.

### 3. Living Documentation

Documentation should evolve with your code. You'll learn workflows for:
- Updating docs as patterns change
- Documenting patterns as they emerge
- Maintaining consistency across the team
- Using AI agents to help with documentation

### 4. Pattern-First Development

Establish and document patterns early. AI agents excel at following patterns once they're clearly defined. You'll learn:
- When to create pattern documentation
- How to structure pattern docs
- How to enforce patterns with AI agents
- How to evolve patterns over time

---

## 🎯 What You'll Be Able to Do

After completing this training, you will be able to:

✅ **Set up** AI agents (Cursor, Claude, Windsurf) for your projects  
✅ **Create effective context documents** that make AI agents project experts  
✅ **Generate code** that follows your patterns automatically  
✅ **Refactor** existing code with AI assistance while maintaining quality  
✅ **Document patterns** as they emerge in your projects  
✅ **Collaborate** with teammates using shared context documents  
✅ **Debug** AI-generated code and improve prompts  
✅ **Maintain** living documentation that stays current  
✅ **Accelerate** your development velocity by 2-3x (based on real-world experience)  

---

## 🚦 Quick Start (Right Now!)

Want to start immediately? Here's what to do:

### Step 1: Choose Your Agent (5 minutes)

- **Want a full IDE?** → Install [Cursor](https://cursor.com)
- **Want deep analysis?** → Install [Claude Desktop](https://claude.ai/download)
- **Want modern workflow?** → Install [Windsurf](https://code.windsurf.ai)

### Step 2: Read This First (20 minutes)

→ [`docs/context-documents/README.md`](./docs/context-documents/README.md)

This is THE most important document. It teaches you how to create context documents that make AI agents effective.

### Step 3: Create Your First Context Document (15 minutes)

Create a file in your project root:
- For Cursor: `.cursorrules`
- For Claude: `CLAUDE.md`
- For Windsurf: `AGENTS.md`

Start with this template:

```markdown
# [Your Project Name] - AI Assistant Context

## Tech Stack
- [Your technologies]

## Key Patterns
- [Your main patterns]

## Critical Rules
- [Your most important rules]

## Project Structure
- [Your folder organization]
```

### Step 4: Try It! (10 minutes)

Ask your AI agent:
- "Explain the structure of this project"
- "Create a new [component/endpoint/function] following our patterns"
- "Review this code for potential issues"

### Step 5: Iterate and Improve

As you work, add more context to your document. The AI agent will get better and better at understanding your project.

---

## 🤝 Who This Is For

### Perfect For:
- ✅ Developers new to AI-augmented development
- ✅ Teams wanting to adopt AI agents consistently
- ✅ Engineers who tried AI coding tools but got mediocre results
- ✅ Tech leads establishing patterns for AI collaboration
- ✅ Anyone who wants to code faster without sacrificing quality

### Not Necessary For:
- ❌ Experienced AI-augmented developers with established workflows
- ❌ Teams already using context documents effectively
- ❌ Developers who already achieve consistent results with AI agents

---

## 📊 Real-World Results

These patterns and practices are based on the **Starshare** project, where:

- **Development velocity** increased 2-3x for routine tasks
- **Code consistency** improved dramatically with documented patterns
- **Onboarding time** for new developers dropped from weeks to days
- **Documentation** stayed current because AI agents help maintain it
- **21+ established patterns** documented and followed automatically

Your results may vary, but the patterns work.

---

## 🎁 What Makes This Training Different

### 1. Based on Real Production Experience
Not theoretical concepts—these are patterns used in a real full-stack application.

### 2. Focuses on the Secret Sauce
Most tutorials focus on prompts. This training focuses on **context documents**—the real key to success.

### 3. Comprehensive Yet Practical
Covers everything from setup to advanced collaboration, but stays practical and actionable.

### 4. Agent-Agnostic Principles
Learn principles that work across Cursor, Claude, Windsurf, and future AI agents.

### 5. Team-Ready
Includes collaboration workflows, not just individual developer practices.

---

## 🗺️ Your Learning Journey Starts Here

I've designed this training to take you from "What's an AI agent?" to "I'm shipping features 3x faster" in a matter of hours, not weeks.

**The path is simple**:

1. **Understand** what AI agents can and can't do
2. **Learn** how to create effective context documents
3. **Practice** with your own projects
4. **Iterate** and improve your workflows
5. **Share** patterns with your team

---

## 📖 Two Ways to Begin

### Option A: Deep Dive

Start with [`docs/README.md`](./docs/README.md) and follow the complete reading path. You'll build comprehensive understanding of all aspects of AI-augmented development.

**Best for**: Individual learning, establishing team practices, comprehensive understanding

### Option B: Visual Overview

Start with `index.html` (coming soon) for an interactive slide presentation that covers the essentials quickly.

**Best for**: Team training sessions, quick overviews, presentations

---

## 🤗 A Note from Your Trainer

I've been where you are. When I first started using AI agents, I treated them like fancy autocomplete. The results were... disappointing. Generic code, inconsistent patterns, constant corrections.

Then I discovered the secret: **context documents**.

Once I learned to create comprehensive context documents that explained my project's architecture, patterns, and conventions, everything changed. The AI agents became genuine collaborators who understood my codebase as well as I did (sometimes better—they never forget patterns!).

This training teaches you everything I wish I'd known from day one. You don't have to make the same mistakes I did. Follow this path, and you'll be productive with AI agents in hours, not months.

The future of software development is here. It's not about AI replacing developers—it's about developers with AI partners being 10x more productive than developers without them.

**Ready to join the future?** 

👉 **Start here**: [`docs/README.md`](./docs/README.md)

Happy coding! 🚀

---

## 📞 Questions or Feedback?

This is a living training resource. If you have questions, find issues, or want to suggest improvements, please contribute back to help other developers on their journey.

---

**Version**: 1.0 | **Last Updated**: 2025-12-15 | **License**: MIT

