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
