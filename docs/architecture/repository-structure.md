# Repository Structure

Detailed folder structure and organization principles of the FS Wiki project.

## Overview

```
fswiki/
├── README.md                    # Main project documentation
├── CONTRIBUTING.md              # Contribution guide
├── ROADMAP.md                   # Project roadmap
├── STYLE_GUIDE.md              # Writing standards
├── CODE_OF_CONDUCT.md          # Code of conduct
├── LICENSE                      # MIT License
├── .gitignore                   # Git ignore rules
│
├── cybersecurity/               # Cybersecurity
│   ├── README.md
│   ├── defensive-security/
│   ├── ethical-hacking/
│   ├── network-security/
│   ├── vulnerability-assessment/
│   └── incident-response/
│
├── software-development/        # Software Development
│   ├── README.md
│   ├── architecture/
│   ├── best-practices/
│   ├── devops/
│   ├── performance/
│   └── testing/
│
├── linux-sysadmin/             # Linux & System Administration
│   ├── README.md
│   ├── configuration/
│   ├── containerization/
│   ├── automation/
│   ├── monitoring/
│   └── security-hardening/
│
├── hardware-electronics/       # Hardware & Electronics
│   ├── README.md
│   ├── embedded-systems/
│   ├── microcontrollers/
│   ├── pcb-design/
│   ├── hardware-security/
│   └── iot/
│
├── 3d-printing/                # 3D Printing & Engineering
│   ├── README.md
│   ├── modeling/
│   ├── materials/
│   ├── post-processing/
│   ├── mechanical-design/
│   └── prototyping/
│
├── resources/                  # Additional Resources
│   ├── README.md
│   ├── tools/
│   ├── references/
│   ├── cheatsheets/
│   └── templates/
│
├── docs/                       # Project Documentation
│   ├── architecture/
│   │   └── repository-structure.md (this file)
│   ├── guidelines/
│   └── templates/
│       ├── article-template.md
│       └── cybersecurity-article-template.md
│
└── assets/                     # Media Files
    └── images/
```

## Organization Principles

### 1. Categorization

Each main category:
- Covers a single topic area
- Has its own README.md file
- Is divided into logical subcategories

### 2. Hierarchy

```
Category
  └── Sub-category
      └── Article
```

### 3. File Naming

- Use lowercase
- Kebab-case format
- Descriptive names
- No Turkish characters

Examples:
- ✅ `network-segmentation-guide.md`
- ✅ `docker-container-security.md`
- ❌ `Network_Segmentation.md`
- ❌ `docker container guide.md`

## Content Organization

### Article Placement

**Rule:** Each article is placed in the most specific appropriate subcategory.

Example:
- "Docker Security Best Practices" → `linux-sysadmin/containerization/`
- "Network Segmentation for Security" → `cybersecurity/defensive-security/`
- "3D Printed Enclosure for Raspberry Pi" → `3d-printing/mechanical-design/`

### Cross-Referencing

Related content:
- Linked in related articles section
- Related categories specified in each category README

## File Types

### Markdown Files (.md)

- Articles
- README files
- Documentation

### Other Files

- **Images:** In `assets/images/` folder
- **Templates:** In `resources/templates/` or `docs/templates/`
- **Configuration:** In root directory (`.gitignore`, etc.)

## Scalability

### Adding New Category

When adding a new category:
1. Create folder in root directory
2. Add `README.md` (with category description)
3. Update main `README.md`
4. Create relevant subcategories

### Adding New Subcategory

When adding a new subcategory:
1. Create subfolder in relevant category folder
2. Update category `README.md`
3. Move/add relevant articles

## Maintenance Notes

### Regular Tasks

1. **Broken Link Check:**
   - Are internal links working?
   - Are external links active?

2. **Organization Review:**
   - Are articles in the right place?
   - Is a new subcategory needed?

3. **README Updates:**
   - Are category READMEs up to date?
   - Is content list correct?

## Example Structure

### Scenario: Network Security Category

```
cybersecurity/
├── README.md
├── network-security/
│   ├── vpn-setup-guide.md
│   ├── firewall-configuration.md
│   ├── network-segmentation.md
│   └── ids-ips-setup.md
├── defensive-security/
│   └── ...
```

Each article:
- Covers a specific topic
- Appropriate length (500-3000 words)
- Linked to related articles

---

**Last Updated:** 2024 Q1
