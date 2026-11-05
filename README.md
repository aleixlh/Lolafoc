# Lola Foc · website

Editorial drag / fashion portfolio with a scroll-linked, reversible Three.js figure.

## Source and deployment

- `index.html`: self-contained reference version for editing/preview.
- `public/index.html`: identical production file served as a Worker static asset.
- `wrangler.jsonc`: Workers static-assets configuration for the existing Cloudflare Worker `silent-scene-260c`.

Cloudflare Workers Builds can connect this repository and auto-deploy `main`. In Cloudflare, open **Workers & Pages → silent-scene-260c → Settings → Builds → Connect** and choose **aleixlh/Lolafoc**, branch `main`. Deploy command: `npx wrangler deploy`; no build command needed. This integration has NOT been confirmed in this session; a GitHub commit is not evidence of a live deploy.

**Do not create a second Worker or change DNS/routes to enable this.** The existing Worker has been observed serving `https://lolafoc.com/` and its workers.dev address. Verify current configuration and deployment status before connecting Builds.

## Development and design

This is intentionally a stylised 3D couture sculpture, **not a scan or faithful likeness** of Lola Foc. The current version improves the camera framing to avoid cut-off boots and headpiece and adds face, jewellery and corset accents. It preserves the directional scroll rotation and reduced-motion accessibility behaviour.

The 3D scene imports pinned Three.js from jsDelivr. It needs WebGL and internet access to render; the page has a visible fallback if it cannot load. Contact actions open [Lola's Instagram](https://www.instagram.com/lola.foc/).

The root and public HTML currently mirror one another. Keep both synchronised when editing; future development can introduce a build step to remove that duplication.

## Publishing safety

Only the configured Worker `silent-scene-260c` is targeted; no MX Labs resources or DNS records are managed by this repository.
