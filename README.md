# UCL CRM – Gecko form CSS

Custom stylesheets for GeckoEngage public forms.

| File | Layout | Status |
| --- | --- | --- |
| `modern.css` | Modern – hero image header, form on a floating card | v0.1 |
| `modern-minimal.css` | Modern – plain white page, accent bar, no hero image or card (imports `modern.css`) | main |

Import **one** of them. For the minimal frame, swap `modern.css` for `modern-minimal.css` in the URLs below.

## Where it applies

Gecko only injects a form's **Custom CSS** into its embed view (`/public/#/iframe/<form-id>`, used when the form is embedded on a webpage). The full-page Modern link (`/public/#/modern/<form-id>`) ignores it. The stylesheets work in both views; the Modern-only parts (header, card, page background, accent bar) simply don't appear in embeds.

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

jsDelivr caches `@main` for up to 12 hours, and tells browsers they can keep the file for 7 days.

- While iterating: after pushing, open `https://purge.jsdelivr.net/gh/tapp1993/ucl-crm-gecko-form-css@main/modern.css` (it can take a minute, and sometimes a second purge, to switch over), then hard-refresh the form.
- For live forms: pin a tag (`@v0`, `@v1` …) and change the URL in Gecko when you release a new version. That way nobody gets a stale cached copy, and a push to `main` never changes a live form unexpectedly.

## Customising

All colours, radii and spacing are CSS custom properties in `:root` at the top of `modern.css`. Override `--gf-accent` (and its `-hover`, `-soft`, `-ring` partners) to rebrand.

## Test form

https://app.geckoform.com/public/#/modern/21FO00yhtoozeq00irj8vg9aws
