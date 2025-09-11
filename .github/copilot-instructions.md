# AI-Prompts Repository Instructions

**ALWAYS follow these instructions first and fallback to additional search and context gathering ONLY if the information in these instructions is incomplete or found to be in error.**

The ai-prompts repository is a documentation-focused educational resource containing AI/LLM prompts, use cases, and materials in Spanish. This is NOT a traditional code repository - there are no build processes, test suites, or runtime environments to manage.

## Repository Structure

This repository contains 251 markdown files organized in a hierarchical directory structure under `/documentos/`. Key directories include:
- `documentos/prompts/` - Core prompt examples and best practices
- `documentos/ingenieriaDePrompts/` - Prompt engineering techniques and patterns  
- `documentos/casosDeUso/` - Use cases and practical applications
- `documentos/imagenes/` - Supporting images and diagrams
- `documentos/itinerarios/` - Learning paths and curricula

## Working Effectively

### Initial Repository Setup
- Clone the repository: `git clone <repo-url>`
- Navigate to repository root: `cd ai-prompts`
- Review existing guidelines: `cat CLAUDE.md`
- Explore structure: `tree -L 3 -d` or `find documentos -type d | head -20`

### Navigation and Exploration
- **TIMING**: Repository exploration takes <1 second. NEVER set timeouts over 30 seconds for basic operations.
- List all markdown files: `find documentos -name "*.md" | wc -l` (takes <0.01 seconds)
- Search content: `grep -r "keyword" documentos` (takes <0.1 seconds)  
- Find specific topics: `find documentos -name "*keyword*"`

### Document Validation
- **NO BUILD PROCESS EXISTS** - This repository contains only documentation
- Validate file integrity: `find documentos -name "*.md" | head -10 | xargs ls -la | wc -l`
- Check relative links exist: `ls documentos/intro.md documentos/LLMs.md` (validates common links)
- Verify navigation patterns: `grep -l "div align=right" documentos/*/README.md | head -3`
- **TIMING**: File validation operations complete in <5 seconds total

### Content Standards and Guidelines
Always follow the established patterns from `.github/CLAUDE.md`:

#### File Naming Conventions  
- Use descriptive lowercase filenames with camelCase when needed
- Avoid spaces (use hyphens or camelCase)
- Create README.md in each directory for navigation

#### Markdown Style Requirements
- Use headers hierarchically (# for titles, ## for sections)
- Include navigation elements at top of documents following existing pattern:
  ```markdown
  <div align=right>
  |[![](badge-links...)|
  |-:|
  </div>
  ```
- Reference other documents using relative links: `[text](/documentos/path/file.md)`
- Use tables for structured comparison information
- Include image references with width specifications: `<img src="path" width=50%>`

#### Git Workflow
- Commit messages should be concise and descriptive
- Prefix commits with context: "New:", "Fix:", "Update:"
- Keep commits focused on single logical changes

## Validation Requirements

### **CRITICAL**: No Build/Test Operations Required
- **DO NOT** attempt to run npm install, make, or any build commands - NONE EXIST
- **DO NOT** look for package.json, Makefile, or build scripts - NONE EXIST  
- **DO NOT** attempt to start servers or applications - NOT APPLICABLE

### Manual Validation Steps
After making changes to markdown content:

1. **Link Validation** (takes <10 seconds):
   ```bash
   # Verify commonly referenced files exist
   ls documentos/intro.md documentos/LLMs.md documentos/prompts/README.md
   ```

2. **Content Structure Check** (takes <5 seconds):
   ```bash
   # Ensure new files follow naming conventions
   find . -name "* *" -type f  # Should return no results (no spaces in filenames)
   ```

3. **Navigation Consistency** (manual review required):
   - Verify navigation badge bar follows existing pattern
   - Check relative links point to existing files
   - Ensure Spanish language consistency maintained

### **TIMING EXPECTATIONS**
- **File exploration**: <1 second for any operation
- **Content search**: <0.1 seconds across all 251 files  
- **Link validation**: <10 seconds for comprehensive check
- **NEVER CANCEL**: No operations should take more than 30 seconds

## Key Repository Locations

### Frequently Accessed Files
- `/README.md` - Main repository introduction and navigation
- `/CLAUDE.md` - AI agent working guidelines  
- `/documentos/prompts/README.md` - Core prompts documentation
- `/documentos/ingenieriaDePrompts/README.md` - Prompt engineering guide
- `/documentos/casosDeUso/README.md` - Use cases and applications

### Important Directory Structure
```
/documentos/
├── prompts/           # Core prompt examples and theory
├── ingenieriaDePrompts/ # Advanced techniques and patterns  
├── casosDeUso/        # Practical applications
├── imagenes/          # Supporting visual content
├── itinerarios/       # Learning curricula
└── papers et al/      # Research and academic content
```

### Content Categories
- **Educational Materials**: Organized by learning progression
- **Practical Examples**: Real-world use cases and applications  
- **Visual Resources**: Diagrams, images, and supporting graphics
- **Reference Materials**: Glossaries, bibliographies, external links

## Common Tasks

### Adding New Content
- Create markdown files following naming conventions
- Include proper navigation headers with badge links
- Maintain Spanish language consistency
- Reference existing files using relative links
- Add README.md files for new directories

### Updating Existing Content
- Preserve existing navigation structure  
- Maintain link integrity when moving/renaming files
- Follow established formatting patterns
- Keep content organization consistent

### Content Validation
```bash
# Quick validation commands (all complete in <30 seconds total)
find documentos -name "*.md" | wc -l                    # Count files
grep -l "README" documentos/*/README.md                 # Verify README files  
ls documentos/imagenes/ | head -5                       # Check image resources
find documentos -name "*.md" -exec head -1 {} \; | head # Test file integrity
```

## Repository Characteristics

- **Language**: Primarily Spanish content
- **File Count**: 251 markdown files  
- **No Dependencies**: Pure documentation repository
- **No Build System**: Files are ready-to-use as-is
- **Version Control**: Standard git workflow
- **Content Focus**: AI education, prompts, and practical applications

## What NOT to Do

- **DO NOT** attempt to install dependencies or run build commands
- **DO NOT** look for CI/CD workflows or GitHub Actions
- **DO NOT** expect runtime environments or executable code
- **DO NOT** modify the established navigation badge system without maintaining consistency
- **DO NOT** break existing relative link patterns
- **DO NOT** add files with spaces in names or non-standard naming

## Quick Reference Commands

All commands execute in <30 seconds:

```bash
# Repository overview
tree -L 3 -d                                    # Directory structure
find documentos -name "README.md"               # All README files
grep -r "título_específico" documentos          # Search content

# Validation  
ls documentos/intro.md documentos/LLMs.md       # Verify key files
find . -name "* *" -type f                      # Check for spaces in names
find documentos -name "*.md" | wc -l            # Count markdown files
find documentos -name "*.md" | head -10 | xargs ls -la | wc -l  # File integrity
grep -l "div align=right" documentos/*/README.md | head -3      # Navigation check
```

**Remember**: This repository focuses on educational content quality and navigation consistency, not code functionality. Validate content structure and links rather than build processes.
