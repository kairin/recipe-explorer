# Recipe Explorer - LLM Instructions

> 🔧 **CRITICAL**: This file contains requirements that ALL AI assistants (Claude, Gemini, ChatGPT, etc.) working on this repository MUST follow at ALL times.

## 📋 Table of Contents

1. [Single Source of Truth](#-single-source-of-truth-mandatory)
2. [Project Overview](#-project-overview)
3. [Repository Structure](#-repository-structure)
4. [Development Guidelines](#-development-guidelines)
5. [GitHub CLI (gh) - Preferred Tool](#-github-cli-gh---preferred-tool)
6. [Absolute Prohibitions](#%EF%B8%8F-absolute-prohibitions)
7. [Documentation](#-documentation)

---

## 🔗 Single Source of Truth (MANDATORY)

**AGENTS.md is the canonical instruction file for all AI assistants.**

Symlink Requirements (ENFORCED):
- `CLAUDE.md` → `AGENTS.md` (symlink, not copy)
- `GEMINI.md` → `AGENTS.md` (symlink, not copy)
- `CHATGPT.md` → `AGENTS.md` (symlink, if created)

**ENFORCEMENT**: Never create copies. Edit AGENTS.md only—changes automatically propagate to all symlinked files.

**Violation Detection**:
```bash
# Check if symlinks are in place
file CLAUDE.md GEMINI.md

# If files are regular files instead of symlinks, fix immediately:
rm CLAUDE.md GEMINI.md
ln -s AGENTS.md CLAUDE.md
ln -s AGENTS.md GEMINI.md
git add CLAUDE.md GEMINI.md AGENTS.md
git commit -m "URGENT: Restore symlinks (enforce single source of truth)"
```

---

## 🎯 Project Overview

**Recipe Explorer** is a beautiful, interactive web application that helps users discover delicious rabbit and vegetable recipes. The application features:

- Interactive radar chart for comparing recipe profiles (Hearty Stew vs. Rustic Roast)
- Detailed cooking instructions with step-by-step methods
- Vegetable preparation guides and timing tables
- Responsive design with warm earth color palette (Stone, Amber, and Sage)
- Clean, modern UI built with TailwindCSS

**Repository**: https://github.com/kairin/recipe-explorer

**Live Site**: https://kairin.github.io/recipe-explorer/

---

## 📁 Repository Structure

```
/recipe-explorer/
├── index.html              # Main Recipe Explorer web application
├── documents/              # Source recipe documents
│   └── recipe-ideas.txt   # Original recipe concepts and ideas
├── AGENTS.md              # This file - AI assistant instructions
├── CLAUDE.md              # Symlink → AGENTS.md
└── GEMINI.md              # Symlink → AGENTS.md
```

---

## 🛠️ Development Guidelines

### Technology Stack
- **Frontend**: HTML5, TailwindCSS (via CDN)
- **Visualization**: Chart.js (radar charts)
- **Fonts**: Google Fonts (Inter)
- **Deployment**: GitHub Pages

### File Editing Principles
1. **index.html**: The main application file - edit for UI/UX improvements, recipe content updates, or styling changes
2. **documents/**: Contains source recipe documents and ideas - treat as reference material
3. **Symlinks**: ALWAYS maintain CLAUDE.md and GEMINI.md as symlinks to AGENTS.md

### GitHub Pages Deployment
```bash
# The site is automatically deployed from the main branch
# Any push to main updates the live site at:
# https://kairin.github.io/recipe-explorer/

# To update the site:
git add .
git commit -m "Update: Brief description of changes

🤖 Generated with [Claude Code](https://claude.com/claude-code)
Co-Authored-By: Claude <noreply@anthropic.com>"
git push origin main
```

---

## 🔧 GitHub CLI (gh) - PREFERRED TOOL

**Use `gh` CLI for all GitHub operations:**

| Task | Command |
|------|---------|
| View repository | `gh repo view kairin/recipe-explorer` |
| Create issue | `gh issue create` |
| View issues | `gh issue list` |
| Create PR | `gh pr create` |
| View PRs | `gh pr list` |
| Edit repo settings | `gh repo edit` |

**Examples**:
```bash
# View repository details
gh repo view kairin/recipe-explorer

# Update repository description
gh repo edit kairin/recipe-explorer --description "New description"

# Set homepage URL
gh repo edit kairin/recipe-explorer --homepage "https://kairin.github.io/recipe-explorer/"
```

---

## ⚠️ ABSOLUTE PROHIBITIONS

### DO NOT
- Delete or replace symlinks (CLAUDE.md, GEMINI.md must always be symlinks to AGENTS.md)
- Commit sensitive data (API keys, passwords, personal information)
- Remove the attribution footer from index.html without user permission
- Change the color palette without user approval (Warm Earth theme is intentional)

### DO NOT BYPASS
- Symlink integrity requirements
- GitHub Pages deployment process
- Recipe attribution and sourcing

---

## 📚 Documentation

### Key Files
- **index.html**: Main Recipe Explorer application with interactive features
- **documents/recipe-ideas.txt**: Original source recipe document with detailed cooking methods
- **AGENTS.md**: This file - instructions for AI assistants

### GitHub Pages
- **Production**: https://kairin.github.io/recipe-explorer/
- **Repository**: https://github.com/kairin/recipe-explorer

### Recipe Content
The Recipe Explorer showcases two primary recipes:
1. **Hearty Rabbit & Winter Vegetable Stew**: One-pot braised dish with rich, savory broth
2. **Rustic Rabbit Roast with Vegetable Medley**: Oven-roasted with caramelized vegetables and pan gravy

Both recipes use the same ingredients but offer different cooking methods and flavor profiles, visualized through an interactive radar chart.

---

**CRITICAL**: These requirements ensure consistency and maintainability. All AI assistants must follow these guidelines to preserve the symlink structure and project integrity.

**Version**: 1.0
**Last Updated**: 2025-11-08
**Status**: ACTIVE - MANDATORY COMPLIANCE
**Repository**: https://github.com/kairin/recipe-explorer

### Change Log
- **2025-11-08**: Initial version for recipe-explorer repository
