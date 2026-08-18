# SANO Med Spa — "It's Your Turn" GLP-1 Landing Page

Single-file landing page for the $149 GLP-1 introductory offer.
Built to convert paid traffic into booked consultations.

**Live:** https://USERNAME.github.io/sano-glp1-landing/

## Files

- `index.html` — the landing page
- `thank-you.html` — post-booking confirmation page (noindexed, fires the conversion event)

## Already wired

- **GoHighLevel calendar** — `XUpgAJaixvKu4l0KhOej`, embedded with the auto-resize script
- **Google Tag Manager** — `GTM-NJZ9PBGJ`, head + noscript on both pages
- **dataLayer events**
  - `book_cta_click` on every CTA, with `cta_text` and `cta_section`
  - `appointment_booked` on `thank-you.html` load

## Before going live

1. **Point the calendar at the thank-you page.** In GHL:
   Calendars → your calendar → Confirmation → "Redirect to a custom page" →
   `https://YOUR-DOMAIN/thank-you.html`
2. **Build the GTM triggers.** Custom Event trigger on `appointment_booked` →
   fire Meta `Schedule`, Google Ads conversion, GA4 `generate_lead`.
   Custom Event trigger on `book_cta_click` for mid-funnel diagnostics.
3. **Meta Pixel** — paste the base code in the marked block in `<head>` on both pages,
   or fire it entirely through GTM.
4. **Results photos** — captions currently read "Actual SANO patient". Add the treatment
   and timeframe to each for a meaningful lift in credibility.
5. **Confirm** — written photo releases on file, and that "medically supervised"
   matches how the program is actually staffed.

## Notes

- Everything is inline: CSS, JS, and the three before/after photos (base64). No build step,
  no dependencies, no asset folder. Total page weight ~255KB.
- Fonts load from Google Fonts (Cormorant Garamond, Mulish, Bodoni Moda, Great Vibes)
  as the closest available substitutes for The Seasons, Avenir Next LT Pro, Didot, and
  Merona Island Bold. Mac visitors fall back to real Avenir Next and Didot.
- Brand colors: `#7D7F70` primary, `#E6DFD3` secondary.
