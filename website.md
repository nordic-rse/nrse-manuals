# Nordic-RSE website

We work in the open as much as possible, and our website is our main outward-facing material.

## Source and hosting

[nordic-rse.org](https://nordic-rse.org) is a static site built with [Zola](https://www.getzola.org/) from markdown files, hosted on GitHub Pages. The source is at [nordic-rse/nordic-rse.github.io](https://github.com/nordic-rse/nordic-rse.github.io).

We don't track visitors or use cookies on the website (see the [privacy notice](https://nordic-rse.org/about/governance/privacy/)).

## Content structure

Pages live under `content/`, organized by URL path, e.g. `content/about/`, `content/blog/`, `content/events/`, `content/communities/`, `content/join/`, `content/resources/`. Each event gets its own dated folder under `content/events/`. Static assets (images, CSS, JS) are under `static/`, and Zola/Tera page templates are under `templates/`.

There are also GitHub issue templates for common cases, e.g. a website issue or a seminar series event, under `.github/ISSUE_TEMPLATE/` in the source repo.

## Writing blog posts

Blog posts are named `content/blog/YYYY-MM-DD-slug.md`.

TODO: what kind of content we are looking for in blog posts (e.g. conference/event reports, member spotlights, technical write-ups, community news), and any expectations on length, tone, or review before publishing.

### Use of AI

No fully AI-generated posts. AI tools can help with drafting or summarizing, but a human needs to stay in the loop: read, fact-check, and rewrite in your own voice before publishing. Making a post genuinely engaging — the personal angle, the specific details, the humor, what actually mattered to you about the event or topic — is something AI can't do for you; that part is on the human author.

## Calendar

The [events calendar](https://nordic-rse.org/calendar/) is a separate system from the main website: [nordic-rse/calendar](https://github.com/nordic-rse/calendar) turns `calendars/*.yaml` files (one per calendar: `NordicRSE`, `community`, `conferences`, `other`, `series`) into `.ics` files via [yaml2ics](https://github.com/scientific-python/yaml2ics), and publishes them to GitHub Pages via its own GitHub Actions workflow. The `.ics` feeds are also embedded on the main site (e.g. the Google Calendar embed on the [events page](https://nordic-rse.org/events/#calendar)).

To add or edit an event, edit the relevant `calendars/*.yaml` file in that repository and open a pull request.

## Domain and DNS

TODO: who manages the `nordic-rse.org` domain registration and DNS records. GitHub Pages is configured to serve the custom domain via a `CNAME` set in the deploy workflow, but the domain registrar/DNS provider and who has access to it isn't documented here yet.

## Branding and style assets

Logos (current and old), stickers, and social-media card templates are collected in [nordic-rse/nordic-rse-materials](https://github.com/nordic-rse/nordic-rse-materials), under `graphics/`. Everything there is CC-BY licensed.

## Previewing changes locally

Install [Zola](https://www.getzola.org/documentation/getting-started/installation/), then from the repository root:

```
zola serve
```

## Contribution guidelines

- Anyone can suggest changes via [issues](https://github.com/nordic-rse/nordic-rse.github.io/issues), or work on them directly with a fork and pull request.
- If you want more involvement in the website work, ask the board to be added to the `nordic-rse` GitHub organization.
- Code and templates are MIT licensed; page content is [CC-BY](http://creativecommons.org/licenses/by/4.0/), same as the rest of Nordic-RSE's material — by contributing content you agree to license it this way.
- TODO: content/style conventions (writing style, markdown conventions, image formats/sizes, alt text and other accessibility expectations).
- TODO: commit message or PR conventions, if any.

## Publishing process

Opening a pull request automatically builds a preview of the site, linked in a comment on the PR (`previews/PR<number>/`); the preview is removed once the PR is merged or closed. Pushing or merging to `main` triggers a production build and deploy.

TODO: who is expected/allowed to review and merge pull requests, and whether a review is required before merging.

## Access

All board members are part of the Nordic-RSE GitHub organization. Others can be added upon request.