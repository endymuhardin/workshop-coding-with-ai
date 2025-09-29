# Workshop AI Development Presentation

This repository contains the source code for the "Workshop: Accelerating Software Development with AI Assistant" presentation.

## Generating the Presentation

The presentation is written in Markdown (`presentasi_workshop_ai.md`) and converted to a `reveal.js` HTML slide deck using `pandoc` running inside a Docker container.

### Prerequisites

- Docker must be installed and running.

### Generation Command

To regenerate the presentation after modifying `presentasi_workshop_ai.md`, run the following command from the root of the project directory:

```bash
docker run --rm -v "$(pwd):/data" -w /data/docs pandoc/core presentasi_workshop_ai.md -t revealjs -s -o index.html --metadata title="Workshop AI Development" -V theme=white
```

This command will create/update the `index.html` file in the `docs` directory. You can then open this file in your web browser to view the presentation.
