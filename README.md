# UCL CRM – Gecko form CSS

Custom stylesheets for GeckoEngage public forms.

| File | Layout | Status |
| --- | --- | --- |
| `modern.css` | Modern | v0 |

## Using it in Gecko

Point Gecko's custom stylesheet import at the jsDelivr URL (GitHub's raw URLs are served as `text/plain`, which browsers refuse to load as CSS):

```
https://cdn.jsdelivr.net/gh/tapp1993/ucl-crm-gecko-form-css@main/modern.css
```

If the import box takes CSS rather than a URL:

```css
@import url("https://cdn.jsdelivr.net/gh/tapp1993/ucl-crm-gecko-form-css@main/modern.css");
```

### Caching

jsDelivr caches `@main` for up to 12 hours. After pushing a change, either:

- purge it: open `https://purge.jsdelivr.net/gh/tapp1993/ucl-crm-gecko-form-css@main/modern.css`, or
- for live forms, pin a tag (`@v0`, `@v1` …) so a change to `main` never alters a live form unexpectedly.

## Customising

All colours, radii and spacing are CSS custom properties in `:root` at the top of `modern.css`. Override `--gf-accent` (and its `-hover`, `-soft`, `-ring` partners) to rebrand.

## Test form

https://app.geckoform.com/public/#/modern/21FO00yhtoozeq00irj8vg9aws
