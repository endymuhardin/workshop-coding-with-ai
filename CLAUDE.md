# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a presentation workshop repository containing educational materials about AI-assisted software development. The project structure is minimal with documentation as the primary artifact.

## Project Structure

- `README.md` - Project overview and build instructions
- `docs/` - Contains all presentation materials
  - `presentasi_workshop_ai.md` - Main presentation content in Markdown
  - `index.html` - Generated reveal.js presentation
  - `assets/` - Images, diagrams, and visual assets

## Build Process

The presentation is built using pandoc in a Docker container. This is the primary development workflow:

```bash
# Generate the presentation HTML from Markdown
docker run --rm -v "$(pwd):/data" -w /data/docs pandoc/core presentasi_workshop_ai.md -t revealjs -s -o index.html --metadata title="Workshop AI Development" -V theme=white
```

## Development Commands

- **Build presentation**: Run the Docker command above after editing `docs/presentasi_workshop_ai.md`
- **View presentation**: Open `docs/index.html` in a web browser
- **Edit content**: Modify `docs/presentasi_workshop_ai.md`

## Content Guidelines

The presentation covers AI development trends including:
- Evolution from copy-paste to CLI assistants
- Model Context Protocol (MCP) architecture
- AI integration across SDLC phases
- DevSecOps with AI
- Migration strategies

When making changes:
- Maintain the slide structure with `---` separators
- Keep diagrams in the `assets/` directory
- Update references to assets when adding new visuals
- Test the presentation build after content changes

## Asset Management

Images and diagrams are stored in `docs/assets/`. When adding new visual assets:
- Use descriptive filenames
- Maintain consistent naming convention (snake_case)
- Update references in the Markdown source
- Ensure assets are committed to version control

## Dependencies

- Docker (required for build process)
- No local pandoc installation needed
- No npm/yarn dependencies
- No build scripts or package.json