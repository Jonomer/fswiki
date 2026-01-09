# Style Guide

Writing standards, formatting rules, and content requirements for FS Wiki.

---

## 📋 Table of Contents

- [General Principles](#-general-principles)
- [File Organization](#-file-organization)
- [Markdown Formatting](#-markdown-formatting)
- [Content Structure](#-content-structure)
- [Language and Tone](#-language-and-tone)
- [Code and Examples](#-code-and-examples)
- [Images](#-images)
- [Links and References](#-links-and-references)
- [Special Cases](#-special-cases)

---

## 🎯 General Principles

### 1. Clarity and Accuracy

- ✅ Use clear, understandable language
- ✅ Explain technical terms on first use
- ✅ Provide real and verifiable information
- ✅ Cite sources

### 2. Practical Focus

- ✅ Practical, applicable content over theory
- ✅ Real-world scenarios
- ✅ Step-by-step instructions
- ✅ Troubleshooting sections

### 3. Professionalism

- ✅ High quality standards
- ✅ Consistent formatting
- ✅ Correct grammar and spelling
- ✅ Appropriate technical terminology

---

## 📁 File Organization

### File Naming

**Format:** `kebab-case.md` (lowercase, separated by hyphens)

**Examples:**
```
✅ network-segmentation-guide.md
✅ docker-container-security.md
✅ pcb-design-best-practices.md
✅ 3d-printing-troubleshooting.md

❌ Network_Segmentation_Guide.md
❌ docker container security.md
❌ PCB-Design.md
```

**Rules:**
- Lowercase only
- Hyphens (`-`) between words
- Descriptive and specific names
- Do not use Turkish characters (İ → i, Ş → s, etc.)

### Folder Structure

Use logical subfolders under each category:

```
cybersecurity/
├── defensive-security/
│   ├── network-segmentation-guide.md
│   └── firewall-configuration.md
├── ethical-hacking/
│   └── penetration-testing-methodology.md
└── README.md (for category description)
```

---

## 📝 Markdown Formatting

### Headings

**Hierarchy:**
```markdown
# H1 - Main Title (Page title, used once)
## H2 - Section headings
### H3 - Subsections
#### H4 - Sub-subsections (rarely)
```

**Rules:**
- H1 only at the very beginning of the file, once
- H2 and H3 common usage
- Avoid H4 and below if possible
- Headings should be descriptive

### Text Formatting

```markdown
**Bold** - Important terms, commands
*Italic* - Emphasis, variable names
`Code` - Technical terms, commands, file paths
~~Strikethrough~~ - Outdated information (rarely)
```

**Example:**
```markdown
You can start a container with the `docker run` command. 
**Important:** This operation may require root privileges.
```

### Lists

**Unordered List:**
```markdown
- First item
- Second item
  - Sub-item (2 space indent)
  - Sub-item
- Third item
```

**Ordered List:**
```markdown
1. First step
2. Second step
   1. Sub-step
   2. Sub-step
3. Third step
```

**Checklist:**
```markdown
- [ ] Task to do 1
- [x] Completed task
- [ ] Task to do 2
```

### Blockquotes

```markdown
> **Note:** Used for important information or warnings.

> **Warning:** For situations that require attention.

> **Tip:** For helpful tips.
```

### Code Blocks

**Inline Code:**
```markdown
`command` or `variable_name`
```

**Code Blocks:**
````markdown
```language
code here
```

```bash
docker ps -a
```

```python
def example():
    return "Hello"
```

```yaml
services:
  web:
    image: nginx
```
````

**Language Tags:**
- `bash`, `sh` - Shell commands
- `python`, `javascript`, `go`, etc. - Programming languages
- `yaml`, `json`, `xml` - Configuration files
- `dockerfile`, `docker-compose` - Docker files
- `text` or empty - General text

---

## 📖 Content Structure

### Required Sections

Each article should include this structure:

```markdown
# Article Title

## Summary
[2-3 sentence brief description]

## Prerequisites
- Required knowledge level
- Required tools/software
- Prerequisite information

## Content
[Main content here]

## Examples
[Practical examples, code snippets]

## Conclusion
[Summary and next steps]

## References
- [Source 1](url)
- [Source 2](url)

## Related Articles
- [Article 1](relative-path.md)
- [Article 2](relative-path.md)
```

### Optional Sections

```markdown
## Troubleshooting
[Common problems and solutions]

## Security Notes
[Important security-related notes]

## Best Practices
[Best practices]

## Notes
[Additional notes, warnings]
```

---

## 💬 Language and Tone

### Language Rules

1. **Professional but Accessible:**
   - Use technical terms but explain them
   - Don't overuse jargon
   - Be understandable for beginners too

2. **Use Active Voice:**
   ```
   ✅ "Run the command" (active)
   ❌ "The command should be run" (passive, unnecessarily formal)
   ```

3. **Clear Instructions:**
   ```
   ✅ "Save the file and restart the service"
   ❌ "It is recommended that the file be saved and the service be restarted"
   ```

4. **Second Person (You):**
   - Use "you" in instructions
   - "You" can be used in examples (more friendly)

### Multilingual Support

**Format:** English only (primary language)

**If needed, separate files:**
```
guide-en.md
guide-tr.md
```

**Recommended:** English-only approach for consistency

---

## 💻 Code and Examples

### Code Example Rules

1. **Working Examples:**
   - All code examples should be tested
   - Don't use non-working placeholder code

2. **Descriptive Comments:**
   ```python
   # ✅ Good
   def secure_hash(password: str) -> str:
       """Secure hash function - uses bcrypt"""
       return bcrypt.hashpw(password.encode(), bcrypt.gensalt())
   
   # ❌ Bad
   def hash(p):
       return h(p)  # Unclear what it does
   ```

3. **Show Output:**
   ```markdown
   When you run the command:
   
   ```bash
   $ docker ps
   CONTAINER ID   IMAGE     STATUS
   abc123         nginx     Up 2 hours
   ```
   ```

4. **Error Scenarios:**
   ```markdown
   If you encounter an error:
   
   ```bash
   $ docker run ubuntu
   Error: permission denied
   ```
   
   Solution: Use `sudo` or add to docker group.
   ```

### Security Sensitivity

**Never Do:**
- ❌ Real API keys
- ❌ Real passwords or tokens
- ❌ Production database connection information
- ❌ Personal information

**Do:**
- ✅ Placeholders like `YOUR_API_KEY`, `example.com`
- ✅ `.env.example` files
- ✅ Add security notes

---

## 🖼️ Images

### Image Rules

1. **Format:**
   - PNG: Screenshots, diagrams
   - SVG: Vector graphics (preferred)
   - JPG: Photos (rarely)

2. **Size:**
   - Maximum width: 1200px
   - File size: As small as possible (<500KB ideal)

3. **File Naming:**
   ```
   assets/
   ├── images/
   │   ├── network-topology-diagram.png
   │   ├── docker-architecture.svg
   │   └── pcb-design-example.png
   ```

4. **Markdown Usage:**
   ```markdown
   ![Alt text description](path/to/image.png)
   
   *Figure 1: Network topology diagram*
   ```

5. **Accessibility:**
   - Always add alt text
   - Add descriptive title/figure number

---

## 🔗 Links and References

### Internal Links

```markdown
✅ [Article Name](relative/path/to/article.md)
✅ [Heading](#section-id)  # Within same file
```

### External Links

```markdown
✅ [Source Name](https://example.com) - Descriptive text
✅ [RFC 7231](https://tools.ietf.org/html/rfc7231) - HTTP/1.1 specification
```

**Rules:**
- Link text should be descriptive (not just "here")
- Use reliable sources for external links
- Use HTTPS when possible

### Reference Format

```markdown
## References

- [Documentation Title](https://example.com/docs) - Brief description
- [Article Title](https://example.com/article) - Author, Year (optional)
- RFC 7231 - [Hypertext Transfer Protocol](https://tools.ietf.org/html/rfc7231)
```

---

## ⚠️ Special Cases

### Cybersecurity Content

**REQUIRED ADDITIONS:**

```markdown
## ⚠️ Ethical and Legal Warning

This content is intended **solely for educational and legal defensive purposes**.

**IMPORTANT:**
- Use these techniques only on **systems you own** or **systems with explicit permission**
- Unauthorized access is illegal and may result in criminal liability
- Always obtain written permission (penetration testing contract) for ethical hacking
- Do not use this information maliciously

**Legal Disclaimer:** Project owners or contributors cannot be held responsible for any actions taken using this content.
```

### Outdated Content

If content is outdated:

```markdown
> **⚠️ Outdated Content**
> 
> This article was written on [Date] and some information may be outdated.
> Update is planned. Last update: [Date]
```

### Work-in-Progress (WIP)

```markdown
> **🚧 Work in Progress**
> 
> This article is still being written. Content may be incomplete or change.
> Estimated completion: [Date]
```

---

## ✅ Checklist

Before submitting an article:

### Content
- [ ] Is there a summary section?
- [ ] Are prerequisites specified?
- [ ] Is main content complete and accurate?
- [ ] Are examples working?
- [ ] Is there a conclusion section?

### Formatting
- [ ] Is Markdown syntax correct?
- [ ] Is heading hierarchy correct?
- [ ] Are code blocks with correct language tags?
- [ ] Do links work?
- [ ] If there are images, is alt text present?

### Ethical and Legal
- [ ] Is warning added for security content?
- [ ] Is there no sensitive information (API key, password)?
- [ ] Are sources specified?
- [ ] Is there no copyright infringement?

### Quality
- [ ] Was spell-check done?
- [ ] Was technical accuracy checked?
- [ ] Was clear and professional language used?

---

## 📚 Additional Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)
- [Technical Writing Best Practices](https://developers.google.com/tech-writing)
- [CONTRIBUTING.md](CONTRIBUTING.md) - Contribution process

---

**Last Updated:** 2024 Q1
