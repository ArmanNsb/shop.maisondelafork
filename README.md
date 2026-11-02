# Maison De La Fork · Shop page (holiday redesign)

A single static page with no build step and no dependencies. Everything it needs is in this folder; the only thing loaded from outside is the KoHo font from Google Fonts.

```
index.html          the shop page (markup, styles and scripts)
product.html        a sample product page (Abrisham Collection); every product card opens it for now
assets/img/         product photos, Cupid crest, garland, logos, favicon
assets/fonts/       Dahlia (display type)
.nojekyll           tells GitHub Pages to serve the files as they are
```

## Preview on your computer

Open a terminal in this folder and run:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000. Double-clicking `index.html` also works, but some browsers block local fonts from `file://`, so the local server is closer to the real thing.

## Deploy with GitHub Pages

1. Create a repository and upload the **contents** of this folder to its root, so `index.html` sits at the top level. Include the hidden `.nojekyll` file (on a Mac, press Cmd + Shift + . in Finder to see it).
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repository-name>/`.

All paths are relative, so the page works at a subpath as well as on a custom domain.

## Placeholders to confirm

- Holiday items: Lattice Pie $85, Pigeon Pie $95, Holiday Cookies from $120, Madeleine Tower $198 are placeholder prices. Pastel Toot Tower keeps the live $228.
- Order-by dates beside the Holiday collection: Thanksgiving Nov 20, Christmas Dec 18. Placeholders.
- The five Holiday images are AI-assisted studio renders on #ECDFD8, made from real product photos. `hol-pastel.jpg` is a portrait version for the tall feature card.
- Product tiles sit on a 3 px light grid (2 px on mobile). Hovering a photo dissolves it into a close-up of the same piece. The close-ups are crops of the main photos, saved as `*-d.jpg` next to them; when a photo is replaced, replace its `-d` close-up too (or re-crop it). On phones (640 px and narrower) the small tiles show the close-up from the start, since there is no hover; the full-width feature and gift-box cards keep the whole object.
- The add button sits beside the price: an ochre ring at rest that fills and reads "Add" on hover. Once a piece is in the bag, the button becomes a navy quantity stepper (minus, count, plus) and the photo shows an "In bag" tag; going back to zero removes it. The bag icon in the header carries an ochre badge with the total. None of this is connected to a store yet.
- Persian Sweets and Assortments: all boxes are AI-assisted overhead studio renders (`*-s.jpg`), made from real product photos, with the backdrop matched to #ECDFD8. Abrisham and Diba are shown at the same scale, so the size difference between Large and Small reads at a glance. Rumi Blend tea and the Gift Card are AI-assisted studio renders too (`tea-tin-s.jpg`, `gift-card-s.jpg`), so every product photo on the page is now on the same backdrop.
- The story section near the foot of the page opens with the Cupid crest (`crest.webp`, transparent).
- Compose Your Own sits on a brand-blue band (#B8C9E1). Its box photo (`compose-box.jpg`) is an AI-assisted render with the backdrop flattened to exactly the same blue, so the image has no visible edge. If you replace it, keep the background exactly #B8C9E1.
- On phones the announcement bar is hidden and the header itself is brand blue, with the one-line logo (`logo-line-navy.svg`, the footer logo in navy) set flush left. The shipping note still appears in the service row near the foot of the page.
- The two corner sprigs appear only on screens 1400 px wide and up, where there is margin beside the content.

## Product page (sample)

- `product.html` is one designed product page, built from the Abrisham Collection. Every product card in the shop links to it for now; when the real store is connected, each card should open its own product.
- It shares the shop's styles, header, footer and service row, cut straight from `index.html` at build time, so the two pages always match.
- All product text is taken as-is from maisondelafork.com/shop/large-mix-box/: name, price, description, the five cookies (shown as small round photos beside the description), size, allergens, pickup and shipping, and the related products. Nothing has been added. The seasonal corner pieces appear on the shop page only.
- Related products follow the live page, except Pomegranate Toot Tower, which is swapped for the Diba Collection so every card has a studio photo.
- The cart is shared between the two pages and remembered in this browser only (localStorage). It is a design stand-in for the real cart.

## Notes before launch

- This is a design build. The Add to Bag, Search, Sort and newsletter controls are not connected to the store yet; the menu, footer and "Begin" links point to the live maisondelafork.com pages.
- Every product photo is a studio render at 1200 × 900 px, with a hover close-up saved as `*-d.jpg` beside it. The older 300 px photos (`*-g.jpg`) are no longer used on the page.
- Make sure the Dahlia licence covers web use.
