# Diagrams

This folder contains Mermaid source files and rendered artifacts used by the Cuttlefish Operator Web UI.

Files
- block-diagram.mmd
- sequence-diagram.mmd
- block-diagram.svg (generated)
- block-diagram.png (generated)
- sequence-diagram.svg (generated)
- sequence-diagram.png (generated)

Regenerate (requires Node and @mermaid-js/mermaid-cli installed in this project):

npm install
npm run diagrams:build

Docker alternative (no local Node dependencies needed):

docker run --rm -u "$(id -u):$(id -g)" -v "$PWD":/work -w /work ghcr.io/mermaid-js/mermaid-cli sh -lc 'mmdc -i docs/diagrams/block-diagram.mmd -o docs/diagrams/block-diagram.svg && mmdc -i docs/diagrams/sequence-diagram.mmd -o docs/diagrams/sequence-diagram.svg && mmdc -i docs/diagrams/block-diagram.mmd -o docs/diagrams/block-diagram.png && mmdc -i docs/diagrams/sequence-diagram.mmd -o docs/diagrams/sequence-diagram.png'

Notes
- The PNG/SVG files are build artifacts; re-run the command whenever the .mmd files change.
- If Puppeteer needs to download a Chromium binary on first run, it may take a few minutes.
