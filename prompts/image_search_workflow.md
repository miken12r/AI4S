# Workflow: sourcing a curated image for a post

## Purpose
Given the `IMAGE DIRECTION` text from `generate_post.md`, find a small
selection of real (non-AI-generated) candidate images to pair with a post.

## Default mood

Default to bright, festive, saturated imagery — vivid color, open light,
alive — rather than moody/dark/desaturated treatments (established
2026-09-03, after repeated feedback steering away from the darker
cards). Only go moodier when the SOURCE quote's own tone genuinely
calls for it; don't default there.

## Steps

1. **Derive 2-4 search terms from the image direction.**
   Favor mood/atmosphere words over literal objects from the quote itself
   (the point is to evoke, not illustrate). E.g. from "a dim hallway with
   two doors, one lit warm, the other shadowed" → `warm light doorway`,
   `quiet hallway`, `threshold light shadow`.

2. **Search Unsplash, Pexels, and Pixabay in parallel** (established
   2026-09-17 — don't wait until Unsplash comes up short; a lot of the
   best Unsplash matches turn out to be Unsplash+ premium and are
   unusable, so checking all three from the start saves a round-trip):
   - Unsplash (unsplash.com) — free, high-quality, Unsplash License (free
     for commercial use, no attribution legally required). Best curated
     "lifestyle/art" aesthetic, but a meaningful share of good hits are
     Unsplash+ premium — verify license per candidate before proposing it.
   - Pexels (pexels.com) — same license spirit and similar curation
     quality to Unsplash; a good parallel pool, not just a fallback.
   - Pixabay (pixabay.com) — much larger, more permissively licensed
     (CC0-style, no premium tier to hit), and because it includes a lot
     of amateur/hobbyist contributions alongside professional ones, it
     often surfaces literal/niche combinations ("flower growing through
     concrete") that Unsplash and Pexels' more curated aesthetic misses.
     Tradeoff: average quality is more mixed — expect to filter more
     candidates than on the other two.
   - Museum open-access archives (Met Open Access, Wikimedia Commons) —
     best when the mood calls for fine art rather than photography;
     confirm public-domain/CC0 status per item.

3. **Pull a small selection (3-5 candidates), favoring:**
   - Landscape/horizontal orientation (fits LinkedIn's image post crop
     better than portrait or square).
   - Understated, uncluttered compositions — avoid stock-photo cliché
     (handshakes, lightbulbs, people at laptops) which reads as corporate.
   - Real photographic/artistic texture over anything that looks
     AI-generated or overly staged.
   - People in frame are fine when they're not individually
     distinguishable (silhouettes, distant figures) — a human moment
     can reasonably include a human. Don't over-use this: it's a
     permitted option, not a new default, and most cards will still be
     people-free (established 2026-09-09).

4. **Record for each candidate:** source, direct URL, and license note,
   so the final choice can be attributed correctly if needed.

5. **Present the selection** to the user for final pick — this workflow
   surfaces candidates, it doesn't auto-select.

6. **Open every candidate in Chrome** as part of presenting them
   (established 2026-10-09) — don't wait to be asked. Open each
   candidate's photo page in one command with an explicit app, e.g.
   `open -a "Google Chrome" <url1> <url2> ...` — never a plain `open`,
   which lands in the user's default browser (Safari).

## Searching Unsplash through Chrome (established 2026-10-13, revised 2026-10-14)

The fastest reliable way to search Unsplash. Plain web search surfaces
few real photo pages. Unsplash's `/napi/search/photos` endpoint is **not**
dependable: it worked from inside an unsplash.com tab on 2026-10-13 but
returned 401 on 2026-10-14, so read the rendered search page instead.

1. Check the Claude in Chrome extension is connected
   (`list_connected_browsers`). If it's empty, fall back to web search
   plus Openverse (`api.openverse.org/v1/images/?license=cc0,pdm`) and
   tell the user the extension isn't connected.
2. For each of 2-3 mood queries, navigate a tab to
   `https://unsplash.com/s/photos/<query-with-hyphens>?orientation=landscape&license=free`
   (`license=free` keeps Unsplash+ out of the results). Scroll once to
   load more, then collect each `<figure>`'s `/photos/` link, image
   `src` and `alt`. Skip any figure mentioning `plus.unsplash`,
   "Sponsored" or iStock. Use `sessionStorage` to accumulate results
   across navigations, since a navigation resets the page's variables.
3. Replace the page body with a numbered grid of the thumbnails, then
   screenshot it (scroll for more rows). Picking from one contact sheet
   beats opening photo pages one at a time.
4. Close the tab. For the 3-5 picks, WebFetch each photo page to
   confirm the photographer and "Unsplash License" (not Unsplash+), then
   continue with steps 4-6 above.

Downloads: `https://unsplash.com/photos/<id>/download?force=true` via
curl returns the full-resolution original (the id is the last segment
of the photo URL slug). Check its real dimensions with `sips`, because
"landscape" filters still return some portrait originals.

## Notes from testing (2026-08-22)

- Unsplash search results include sponsored iStock/Getty items mixed into
  the grid — skip these; they're paid stock, not Unsplash-licensed, and
  tend to be more staged/corporate-looking anyway.
- Unsplash lazy-loads results as you scroll — if the first screenful
  doesn't have enough good candidates, scroll down rather than assuming
  the search came up short.
- "Mood over literal" search terms (e.g. `warm light doorway` rather than
  anything from the quote text itself) reliably surfaced uncluttered,
  non-corporate results on the first try.
