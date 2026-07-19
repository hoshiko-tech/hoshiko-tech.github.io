# "Built by Hoshiko Tech" footer credit

A small, self-contained credit to drop into the footer of any site built for a
client. It links back to the Simple Websites page and doubles as a referral and
SEO signal.

Live preview: [`index.html`](./index.html) (open in a browser, or visit
`https://www.hoshiko.tech/websites/credit/`).

## How to use

1. Paste the snippet below into the client site's footer.
2. Replace `CLIENT` in `?ref=CLIENT` with a short slug for that client (e.g.
   `?ref=acme-cafe`). This is just so referral clicks are attributable later.
3. That's it. Nothing else to configure.

```html
<a class="hshk-credit" href="https://www.hoshiko.tech/websites/?ref=CLIENT" target="_blank" rel="noopener">
  <svg class="hshk-spark" width="13" height="13" viewBox="0 0 24 24" aria-hidden="true" focusable="false"><defs><linearGradient id="hshk-g" x1="0" y1="0" x2="24" y2="24" gradientUnits="userSpaceOnUse"><stop stop-color="#22d3ee"/><stop offset=".5" stop-color="#818cf8"/><stop offset="1" stop-color="#c084fc"/></linearGradient></defs><path fill="url(#hshk-g)" d="M12 0c.5 6.5 5 11 12 12-7 1-11.5 5.5-12 12-.5-6.5-5-11-12-12 7-1 11.5-5.5 12-12z"/></svg>
  <span>Built by <span class="hshk-name">Hoshiko Tech Ltd</span></span>
</a>
<style>
  .hshk-credit{display:inline-flex;align-items:center;gap:6px;font:500 13px/1.4 ui-sans-serif,system-ui,-apple-system,sans-serif;color:inherit;opacity:.75;text-decoration:none;transition:opacity .2s ease}
  .hshk-credit:hover{opacity:1}
  .hshk-name{background:linear-gradient(135deg,#22d3ee,#818cf8,#c084fc);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;font-weight:600}
  .hshk-spark{flex:none;animation:hshk-tw 2.8s ease-in-out infinite;transition:transform .5s ease}
  .hshk-credit:hover .hshk-spark{transform:rotate(90deg)}
  @keyframes hshk-tw{0%,100%{opacity:.5}50%{opacity:1}}
  @media(prefers-reduced-motion:reduce){.hshk-spark{animation:none}}
</style>
```

## Why it's built this way

- **Plain HTML, no JavaScript.** Works even if scripts fail, and there is nothing
  hosted elsewhere that can break the credit on delivered sites later.
- **Adapts to any footer.** "Built by" inherits the site's own text colour (via
  `color: inherit`), so it stays readable on dark, light, or coloured footers.
  Only the name and sparkle use the brand gradient, so the pop is
  background-independent.
- **Namespaced.** Classes and the gradient `id` are prefixed `hshk-` so they will
  not collide with the client site's own CSS.
- **Accessible.** The sparkle is `aria-hidden` (decorative), and the animation is
  disabled for visitors who prefer reduced motion.

## Notes / options

- **Wording:** change the text to taste (e.g. "Website by Hoshiko Tech"). Keep the
  name inside `<span class="hshk-name">` so it keeps the gradient.
- **SEO:** the link is followed, which helps the Simple Websites page. If you ever
  want to be cautious about many identical footer links across sites, add
  `nofollow` to the `rel` (this removes the SEO benefit).
- **Tracking:** the `?ref=` slug lets you see which client sites send visitors if
  analytics is added later. It has no effect on the page otherwise.
- **This is the single source of truth.** Update the snippet here, then paste the
  new version into future builds. Already-delivered sites keep their copy (a
  static credit can't be changed remotely, which is the trade-off for having no
  runtime dependency).
