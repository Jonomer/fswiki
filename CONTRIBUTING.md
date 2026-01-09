# Contributing Guide

This document explains how you can contribute to the FS Wiki project.

---

## 📋 Table of Contents

- [Code of Conduct](#-code-of-conduct)
- [Types of Contributions](#-types-of-contributions)
- [Getting Started](#-getting-started)
- [Workflow](#-workflow)
- [Writing Standards](#-writing-standards)
- [Review Process](#-review-process)

---

## 📜 Code of Conduct

By contributing to this project, you are expected to follow the rules in [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Brief summary:

- ✅ Be respectful and inclusive
- ✅ Provide constructive feedback
- ✅ Use professional language
- ❌ Do not make personal attacks
- ❌ Do not submit spam or off-topic content

---

## 🎯 Types of Contributions

### 1. Adding Content

- Writing new articles
- Improving existing articles
- Completing missing topics
- Adding code examples and scenarios

### 2. Fixes

- Fixing spelling errors
- Resolving formatting issues
- Updating outdated information
- Fixing broken links

### 3. Documentation

- Improving READMEs
- Clarifying guidelines
- Adding examples
- Translations (if needed)

### 4. Organization

- Content categorization
- Navigation improvements
- Adding cross-referencing

---

## 🚀 Getting Started

### 1. Fork the Repository

Fork the project on GitHub and clone it locally:

```bash
git clone https://github.com/YOUR_USERNAME/fswiki.git
cd fswiki
```

### 2. Add Remote Repository

```bash
git remote add upstream https://github.com/Jonomer/fswiki.git
```

### 3. Create a Branch

Create a new branch for each contribution:

```bash
git checkout -b feature/your-contribution-name
# or
git checkout -b fix/issue-description
```

**Branch Naming Rules:**
- `feature/` - New content or feature
- `fix/` - Bug fix
- `docs/` - Documentation change
- `update/` - Existing content update

---

## 📝 Workflow

### 1. Make Your Changes

- Follow the standards in [STYLE_GUIDE.md](STYLE_GUIDE.md) file
- Produce high-quality, accurate content
- Add sources where necessary

### 2. Commit Messages

Write descriptive and concise commit messages:

```
feat(cybersecurity): Add defensive security best practices article

- Add network segmentation guide
- Include firewall configuration examples
- Add monitoring recommendations

Closes #123
```

**Commit Message Format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Commit Types:**
- `feat`: New content/feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting
- `refactor`: Code/content restructuring
- `update`: Update

### 3. Test

- Check Markdown syntax
- Ensure links work
- Verify formatting is correct

### 4. Push and Open PR

```bash
git add .
git commit -m "feat(category): Description"
git push origin feature/your-contribution-name
```

Then create a Pull Request on GitHub.

---

## ✍️ Writing Standards

### General Rules

1. **Language and Tone**: Professional, technical, but understandable
2. **Format**: Markdown (.md)
3. **Length**: Articles ideally 500-3000 words
4. **Structure**: Clear headings, subheadings, use of lists

### Content Requirements

#### Each Article Should Include:

```markdown
# Article Title

## Summary
Brief description (2-3 sentences)

## Prerequisites
- Required knowledge/tools
- Prerequisites

## Content
[Main content here]

## Examples
[Code examples, scenarios]

## References
- [Link 1](url)
- [Link 2](url)

## Related Articles
- [Article 1](path)
- [Article 2](path)
```

### Ethical and Legal Requirements

⚠️ **CRITICAL**: For cybersecurity content:

- ✅ Only **defensive** and **ethical hacking** focused
- ✅ Indicate it is **for educational purposes**
- ✅ Add **legal warnings**
- ✅ Emphasize that **authorization is required**
- ❌ NO exploit codes or attack tools
- ❌ NO unauthorized access methods

---

## 🔍 Review Process

### Checklist Before Submitting PR

- [ ] Does it comply with [STYLE_GUIDE.md](STYLE_GUIDE.md) standards?
- [ ] Is Markdown format correct?
- [ ] Are there spelling errors? (Spell-check done?)
- [ ] Do links work?
- [ ] If there are images, is alt text added?
- [ ] Are ethical and legal warnings added when required?
- [ ] Are commit messages descriptive?
- [ ] Is there a "Summary" section?

### Review Stages

1. **Automated Checks**: CI/CD (if available)
2. **Initial Review**: Format check by maintainer
3. **Technical Review**: Content accuracy check
4. **Final Approval**: Merge decision

### Feedback

- Reviews will be constructive and respectful
- Explanations will be provided for each feedback
- Direct fixes may be suggested for small changes

---

## 📚 Resources

- [STYLE_GUIDE.md](STYLE_GUIDE.md) - Detailed writing standards
- [ROADMAP.md](ROADMAP.md) - Project roadmap
- [Markdown Guide](https://www.markdownguide.org/) - Markdown reference

---

## ❓ Questions

If you have questions while contributing:

1. Check the [GitHub Discussions](https://github.com/Jonomer/fswiki/discussions) section
2. Open a new Discussion
3. Create an Issue (for short questions)

---

**Thank you for contributing! 🙏**
