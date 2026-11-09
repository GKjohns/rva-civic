# RVA Civic

Data stories about Richmond, Virginia. Some important, some just fun. A landing page today, growing into a set of small interactive widgets backed by public data.

Built with [Nuxt 4](https://nuxt.com) and [Nuxt UI](https://ui.nuxt.com), started from the Nuxt UI starter template.

## Run it

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

## Layout

- `app/pages/index.vue` is the landing page and the list of widget ideas.
- `app/components/WidgetCard.vue` is the card each widget lives in.
- `app/utils/site.ts` holds the site name, description and repo link.

## Checks

```bash
npm run lint
npm run typecheck
npm run build
```
