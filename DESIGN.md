# DESIGN.md

Read this file before changing any HTML, CSS, or copy in this repo. If a rule here conflicts with a default you would normally choose, follow this file.

## Context

- Personal portfolio for Wendy Vang, hosted as a static site on GitHub Pages (username.github.io repo). No server, no build step.
- The current site is the FREEHTML5 "Crew" template: Bootstrap 3, jQuery, Owl Carousel, Waypoints, Animate.css, icomoon and Simple Line Icons fonts, Modernizr, a pink.css theme, Source Sans Pro.
- Audience: recruiters and hiring managers for Cloud Infrastructure and AI Solutions roles. They skim for 30 to 60 seconds. The site's job is to make projects, roles, and contact links easy to find.
- Target look: plain, restrained, professional. One calm accent color. Nothing that draws attention to the design itself.

## Technical approach

- Rebuild as plain semantic HTML plus one `styles.css`. No Bootstrap, jQuery, Owl Carousel, Waypoints, Animate.css, icon fonts, or Modernizr. No JavaScript unless a feature cannot work without it.
- Do not copy markup or CSS from the old template. Work on a branch and leave the old files untouched until the new page is approved.
- Use `header`, `nav`, `main`, `section`, `footer`. Set `lang="en"`. Use CSS custom properties for every color, font, and spacing value below.
- One breakpoint is enough. Single column, readable from 360px wide.
- Keyboard focus must be visible (`:focus-visible` outline in the accent color). Respect `prefers-reduced-motion`.
- Fill in real `<title>`, meta description, `og:title`, `og:description`, `og:image`, and a favicon. Every image gets meaningful alt text or `alt=""` if decorative.

## Decisions

Palette (use only these):

| Token | Hex | Use |
| --- | --- | --- |
| page | `#FFFFFF` | page background |
| surface | `#F4F6F8` | one subtle block at most, such as the contact area |
| text | `#1F2328` | body and headings |
| muted | `#57606A` | dates, secondary lines, footer |
| border | `#D8DEE4` | 1px dividers between entries |
| accent | `#1F4E8C` | links, the primary button, focus outline |
| accent-hover | `#163B6B` | hover state for accent |

Light theme only. The accent never appears as a background wash, gradient, glow, or large fill. The only filled accent element on a screen is the primary button.

Type: IBM Plex Sans for everything (400, 500, 600). Self-host the font files or use the Google Fonts link, with `system-ui, sans-serif` as the fallback. Do not use Inter, Geist, Roboto, Space Grotesk, or any serif display font.

- Body 17px, line-height 1.6. Text column no wider than 68ch.
- h1 clamp(32px, 5vw, 44px), weight 600. h2 24px, weight 600. h3 18px, weight 600. Small text 14px.
- Sentence case everywhere. No all-caps labels, no letter-spaced eyebrows above headings.

Shape and depth: 4px radius on buttons and images, nothing else rounded. No box shadows. Separate entries with a 1px border line, not cards.

Spacing: 8px base unit (8, 16, 24, 48, 72). Sections are 72px apart on desktop and 48px on mobile.

Layout: one centered column, max width 880px, all text left aligned.

```
Wendy Vang                      (h1)
One sentence: what I do and what I am looking for.
GitHub   LinkedIn   Email   Resume (PDF)

About
  Two short paragraphs, then skills as plain grouped text lines.

Projects
  Project name
  What it does and the outcome, in 2 to 3 sentences.
  Stack: ...        Link to the correct repo
  (real screenshot or architecture diagram when available)

Experience and Education share one row pattern:
  [dates, muted]   [role or degree, organization, 1 to 3 factual lines]

Contact
  Email, LinkedIn, GitHub.
```

Repeat the dates-left, details-right row for Experience and Education. Projects are plain entries separated by borders. Do not introduce a second entry style.

## Never do

- Purple, violet, or indigo anywhere. No gradients, gradient text, glows, or colored shadows.
- A carousel, a hero slider, or device mockups.
- A centered hero with a pill badge above the heading.
- Rows of identical cards with a circular icon on top.
- Colored left or top borders on cards or quotes.
- Emoji or icon-font glyphs used as decoration. Social links are plain text links.
- Numbered 1-2-3 markers, stat banners, or testimonial blocks, unless the content truly is a sequence, a measured set of numbers, or a real quote from a named person.
- Fade-in-on-scroll, hover-grow, parallax, or scroll hijacking. Only color transitions on links and buttons (150ms).
- Stock photos. Use a real photo of me, a real screenshot, or no image.
- Arrow glyphs on links or buttons, "WORD — fragment" labels, or meta strings joined with middle dots.

## Copy rules

- Do not invent facts. Employers, dates, metrics, project outcomes, and certifications come from me. Where content is missing, leave a visible `TODO:` comment in the HTML and tell me, instead of writing filler.
- Lead with what was built and what happened, then the stack. Cut self-description adjectives such as passionate, ambitious, eager, and driven.
- Link text names the destination ("WiNDY repository on GitHub"), not "Check it out" or "Learn more".
- No em dashes. Avoid "empower", "unlock", "transform", "seamless", "leverage".
- Plain first person, short sentences.

## Known problems in the current index.html to fix

- The Working Experience section contains lorem ipsum and fake testimonials attributed to "John Doe, CEO FREEHTML5.co". Replace with my real roles (mark `TODO:` and ask me for the details).
- The section with id `contact` is a "Press Releases" block with four lorem ipsum cards. Replace with a real contact section.
- LyricLens links to the WiNDY-Public repo. Both projects use the same image (`img_7.jpg`).
- Education uses the template's pricing classes (`price-box`, `pricing-plan`). "Univeristy" is misspelled.
- Footer says "2015 Free Crew" and shows Twitter, Facebook, YouTube, Pinterest, Instagram, and Dribbble icons with `href="#"`. Keep only links I actually use (GitHub, LinkedIn, email).
- Skill icons do not match their topics (mustache, heart, rocket, eye). Remove icons.
- Open Graph and Twitter meta tags are empty. The meta description credits the template. The page title includes "Ambitious ITI Student".
- Heading tags are mismatched in the hero (`<h2>` closed with `</h3>`). Hero alt text reads "Free HTML5 Template by FREEHTML5.co".

## Before you finish

1. List every rule in this file and mark it satisfied or not. Report any you could not satisfy and why.
2. Check text contrast against the palette above (all pairs must meet WCAG AA, 4.5:1 for body text).
3. Open the page at 360px and 1280px wide and confirm nothing scrolls sideways.
4. Search the output for em dashes, `lorem`, `FREEHTML5`, `John Doe`, and `href="#"`. None should remain.
