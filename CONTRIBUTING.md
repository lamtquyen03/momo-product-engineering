# CONTRIBUTING.md

## How to Push to GitHub

This repository is set up and ready to be pushed to GitHub. Follow these steps:

### 1. Create a GitHub Repository

1. Go to [github.com](https://github.com) and log in
2. Click **"New"** to create a new repository
3. Name it: `momo-product-engineering`
4. Choose visibility: **Public** (for team collaboration) or **Private** (for internal only)
5. **Do NOT** initialize with README (we already have one)
6. Click **Create repository**

### 2. Push Local Repository to GitHub

Once you have your GitHub repository URL (e.g., `https://github.com/yourusername/momo-product-engineering.git`):

```bash
# Add remote origin
git remote add origin https://github.com/yourusername/momo-product-engineering.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

### 3. Verify Push

Visit your GitHub repository URL in a browser. You should see all the files and folders.

---

## Branching Strategy

We use a simple git workflow:

```
main (production-ready)
  ├── feature/dashboard-v2
  ├── feature/sme-financing
  └── docs/roadmap-update
```

### Creating a Feature Branch

```bash
git checkout -b feature/your-feature-name
# Make changes
git add .
git commit -m "Description of changes"
git push -u origin feature/your-feature-name
# Create Pull Request on GitHub
```

---

## Commit Message Format

Follow this format for clear commit history:

```
[TYPE] Brief description (50 chars max)

Detailed explanation if needed.
- What changed
- Why it changed
- Any related issues

# Types:
# [FEAT] - New feature
# [UPDATE] - Updates to existing content
# [FIX] - Bug fixes
# [DOCS] - Documentation changes
# [REFACTOR] - Code/structure reorganization
# [DESIGN] - Design updates/mockups
```

### Examples

```bash
# Good
git commit -m "[FEAT] Add SME merchant dashboard design

- Complete wireframes for home screen
- Data schema for analytics layer
- API contracts for dashboard endpoints
- Covers Q2 2025 launch requirements"

# Also good
git commit -m "[DOCS] Update roadmap for H2 2025"

git commit -m "[UPDATE] Financial services product specs"
```

---

## File Organization

```
momo-product-engineering/
├── README.md                           # Main overview
├── .gitignore                          # Git ignore rules
├── CONTRIBUTING.md                     # This file
├── docs/
│   ├── STRATEGY.md                    # Strategic direction
│   ├── ROADMAP.md                     # Timeline & milestones
│   └── OKR_FRAMEWORK.md               # Goals & metrics
├── product-areas/
│   ├── payments.md                    # Payment services
│   ├── financial-services.md          # Invest & insurance
│   ├── business-solutions.md          # Merchant tools
│   ├── growth-discovery.md            # Personalization
│   ├── lifestyle.md                   # Entertainment & utilities
│   ├── security-compliance.md         # eKYC & risk
│   └── sme-merchants-product-design.md # SME solutions (NEW)
├── diagrams/
│   ├── ecosystem.mmd                  # Product map
│   ├── user-journey.mmd               # Customer flow
│   ├── payment-flow.mmd               # Transaction flow
│   └── growth-loops.mmd               # Growth mechanics
└── templates/
    ├── PRD_TEMPLATE.md                # Product requirements
    ├── FEATURE_SPEC_TEMPLATE.md       # Feature specs
    └── METRICS_TEMPLATE.md            # KPI tracking
```

---

## Documentation Standards

### Markdown Headers
- Use `#` for main title
- Use `##` for major sections
- Use `###` for subsections

### Mermaid Diagrams
- Use descriptive titles
- Color code by product area:
  - **Blue (#2196F3)**: Payments & Transfer
  - **Orange (#FF9800)**: Financial Services
  - **Green (#4CAF50)**: Business Solutions
  - **Purple (#9C27B0)**: Growth & Discovery
  - **Red (#FF1744)**: Core Systems
  - **Cyan (#00BCD4)**: User-facing
  - **Yellow (#FFC107)**: Growth & Engagement

### Tables
- Use for comparative data
- Include units (%, K₫, hours, etc.)
- Sort by importance or frequency

---

## Review Process

### Before Pushing

1. ✅ Run spell check
2. ✅ Verify all links work
3. ✅ Check Mermaid diagram syntax
4. ✅ Ensure consistent formatting
5. ✅ No sensitive data (API keys, passwords)

### Pull Request Template

```markdown
## Changes
- [ ] New feature
- [ ] Updated documentation
- [ ] Design updates
- [ ] Other: ___

## What's Changed
Brief summary of what changed and why.

## Related Issues
Closes #123

## Checklist
- [ ] Spell checked
- [ ] Diagrams render correctly
- [ ] Links work
- [ ] No sensitive data
- [ ] Consistent formatting
```

---

## Collaboration Tips

### Updating Product Specs
- Always get Product Manager approval first
- Link to related diagrams
- Include metrics/KPIs
- Add timeline & ownership

### Adding New Product Area
1. Create new file in `product-areas/`
2. Follow existing template
3. Include 3-5 Mermaid diagrams
4. Add to main README
5. Cross-link related areas

### Sharing Designs
- Link Figma files in product specs
- Embed screenshots in markdown
- Use consistent naming (e.g., `Dashboard-v2-Home`)
- Version designs (v1, v2, etc.)

---

## CI/CD Setup (Future)

Once set up, consider adding:

```bash
# Markdown linting
npm install -D markdownlint

# Spell checking
npm install -D cspell

# Link checking
npm install -D markdown-link-check
```

Run in CI/CD pipeline to auto-validate documentation.

---

## Support & Questions

**Repository Owner**: MoMo Product Engineering Team  
**Email**: team@momo.vn  
**Slack Channel**: #product-engineering  

For questions, file an issue on GitHub or reach out to the team.

---

**Last Updated**: July 2026
