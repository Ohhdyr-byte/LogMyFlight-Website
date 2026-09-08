# LogMyFlight Promotional Website

## Summary

Build a polished, fully static Astro 7 website for LogMyFlight, aimed primarily at student and private pilots. The site will promote fast, customizable flight logging, emphasize privacy-first CloudKit synchronization, and guide visitors toward downloading the free iPhone/iPad app.

The visual direction will use Apple-inspired principles—generous whitespace, strong typography, refined surfaces, responsive layouts, and restrained animation—without copying Apple’s proprietary design or branding.

## Implementation Changes

- Create a shared Astro layout, navigation, footer, global design tokens, and reusable marketing/legal components using Astro and plain CSS with no client framework.
- Support automatic light and dark themes through `prefers-color-scheme`, accessible contrast, visible focus states, semantic HTML, keyboard navigation, and reduced-motion preferences.
- Centralize editable values in one typed site configuration: app and developer names, support email, App Store URL, production domain, feature and FAQ copy, privacy-policy effective date, and screenshot asset paths.
- Keep all unconfirmed product copy visibly marked as provisional/TODO. Do not invent export, compliance, currency, backup, or regulatory capabilities.

### Homepage

- Add sticky responsive navigation, a conversion-focused hero, App Store CTA, app icon placeholder, and prominent iPhone screenshot placeholder.
- Present only confirmed themes: fast flight entry, user customization, private CloudKit synchronization, and explicitly selected photo attachments.
- Add three reusable screenshot placeholders, a privacy/trust section, closing CTA, and subtle reduced-motion-safe effects.

### Supporting Routes

- `/support`: accessible FAQ for setup, flight records, customization, CloudKit sync, photo access, and privacy, followed by a prefilled support email link.
- `/privacy`: explain private CloudKit storage, selected-photo access, no developer access to flight records, and no analytics, advertising, or tracking.
- `/terms`: cover permitted use, ownership, availability, limitations, and clarify that LogMyFlight is a recordkeeping aid rather than an authoritative source of regulatory compliance.

## Deployment and Discoverability

- Keep static output, centralize the canonical site URL, and add a GitHub Pages deployment workflow.
- Include a placeholder custom-domain configuration and document setup before launch.
- Add per-page metadata, canonical links, social metadata, sitemap, robots.txt, JSON-LD, and a custom 404 page.
- Use system fonts and add no cookies, analytics, form services, or consent banner.

## Test Plan

- Run the production build and verify every route and generated metadata endpoint.
- Test responsive layouts, light/dark themes, keyboard navigation, focus states, semantics, alt text, and reduced-motion behavior.
- Verify centralized App Store/support links and visibly flag launch placeholders.
- Run accessibility, SEO, best-practice, and performance checks before launch.
- Confirm all factual claims match the released app before App Store submission.

## Assumptions and Launch Checklist

- Product name: LogMyFlight; platforms: iPhone and iPad.
- Initial audience: student and private pilots, with customization suitable for broader pilot needs.
- The app is free at launch; unreleased Pro features are not advertised.
- The website and app currently contain no third-party analytics, tracking, or advertising.
- Developer name, support email, custom domain, App Store URL, app icon, final copy, and screenshots remain centralized placeholders until supplied.
- All public placeholders, legal identifiers, and links must be finalized before App Store review.
- Privacy and terms copy are starter drafts rather than legal advice and should be reviewed for applicable jurisdictions before publication.

## Aviation Motion Enhancement

- Add a decorative SVG flight path from the hero through the feature cards to the privacy section, with a minimal aircraft following scroll progress and activating route waypoints.
- Keep the implementation dependency-free using one passive scroll listener, `requestAnimationFrame`, cached geometry, and an intersection observer for content reveals.
- Add restrained hero cloud drift and slight screenshot-device depth while keeping all interactive content above the decorative layer.
- Use a simplified route on mobile. Under reduced-motion preferences, show a faint static route, hide the aircraft, disable cloud drift and parallax, and reveal all content immediately.
- Keep support and legal routes calm and unchanged.

## Customization-First Homepage

- Make “Your logbook, your way” the hero promise, supported by ease of use rather than presenting fast entry as the primary differentiator.
- Add an adaptive light/dark HTML/CSS product demonstration based on the supplied app references. It shows Instrument Time and IFR Actual being hidden from both settings and a flight-entry preview while essential fields remain.
- Auto-play the comparison once on viewport entry and provide accessible state, pause/play, and replay controls. Manual input cancels automatic changes; reduced-motion mode starts in the simplified state.
- Explain that most built-in fields can be shown or hidden, pilots can create fields such as NM Travelled, dashboard cards are selectable, and records support relevant filters.
- Order supporting stories as easy entry, selected insights/filtering, privacy, then photos as a secondary benefit.

## Direct Field-Toggle Demo Refinement

- Remove automatic playback, replay, and preset-state controls from the customization demonstration.
- Make Day, Night, Instrument Time, and IFR Actual independent accessible switches that immediately show or hide their matching flight-entry preview rows; required Off Block and On Block fields remain fixed.
- Present both reconstructed screens at a modern iPhone `9 / 19.5` aspect ratio and retain side-by-side phones at supported responsive widths.
- Replace the font-based add symbol with mathematically centered inline SVG geometry.
- Announce each visibility change through a live region, disable row transitions for reduced motion, and show every field when JavaScript is unavailable.
