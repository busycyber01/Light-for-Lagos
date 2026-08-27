# Light for Lagos

A single-page landing site for a free electricity token giveaway across Lagos State. Visitors read about the program and submit an application form (name, phone, email, address, LGA, meter number) that's delivered straight to a Formspree inbox — no backend required.

## What's inside

- `index.html` — the entire site: markup, styles, and scripts in one file. No build step.

## Getting it running

1. Open `index.html` in a browser to preview it locally — everything renders as-is.
2. To publish it, upload `index.html` to any static host (GitHub Pages, Netlify, Vercel, or plain shared hosting all work).

## Before you go live

**Connect the form to Formspree.** In `index.html`, find:

```html
<form id="tokenForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

Replace `YOUR_FORM_ID` with your real endpoint from [formspree.io](https://formspree.io). Name the form **"Light for Lagos — Token Applications"** in the Formspree dashboard so it's easy to find later.

**Verify the LGA list.** The dropdown includes all 20 Lagos State LGAs — double-check it matches the areas you're actually able to serve, and trim it if the program is limited to fewer LGAs at launch.

**Decide on capacity messaging.** If applications outpace your token supply, you'll want a way to close the form or show a "fully subscribed" state — not built in yet.

## How the form behaves

Submissions are sent via AJAX (fetch), so the page never reloads — applicants see an inline "Thank you" message on success, or an inline error if the request fails, and the form itself is replaced by the success message once it goes through.

## Structure of the page

1. **Hero** — headline, CTA, animated sample token display
2. **Story** — why the program exists
3. **How it works** — 4-step process (apply → verify → token sent → load it)
4. **Eligibility** — who qualifies
5. **Application form** — the 5 essential fields
6. **FAQ** — addresses trust/legitimacy questions upfront
7. **Footer** — contact link

## Notes

- No frameworks, no dependencies beyond Google Fonts (Space Grotesk, JetBrains Mono, Inter) loaded via CDN.
- Fully responsive down to mobile.
- No sensitive data (bank details, PINs, NIN/BVN) is collected or should ever be added to this form — flag that clearly if you extend it.
