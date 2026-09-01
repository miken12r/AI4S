# Prompt: Generate a "Humanity Moment of the Day" LinkedIn post

## Purpose
Produce one LinkedIn post that interrupts a feed of business/commercial
content with something honest, reflective, and moving — drawn from the
humanities and culture (poetry, popular music, fiction, biography, art,
literature, etc.).

## Inputs
- `SOURCE`: a quote, lyric, passage, or excerpt (with attribution: author/
  artist, work title, year if known).
- (optional) `THEME`: a mood or thread to steer selection/commentary
  (e.g. resilience, wonder, grief, ordinary courage).

## Cadence

Posts run on a traditional work week — weekdays only, no weekend
posts. "Humanity Moment of the Day" stays the title under this
cadence (the same convention as "Daily" business newsletters that are
implicitly Mon–Fri).

## Card dimensions

Quote card artboards are 1200×627px (landscape, 1.91:1) — LinkedIn's
standard feed image size (established 2026-09-01, replacing the
earlier 1200×1500 portrait format). Always include the "Humanity
Moment of the Day" footer label within the frame at design time
(e.g. `bottom: 28px`) rather than relying on the export to capture
content below the visible content flow — some exports crop to less
than the full artboard height. For a full-bleed photo background, use
an `<img>` tag with `object-fit: cover` (see
[[feedback_ai4s_img_not_background_image]] — CSS `background-image`
is unreliable in this tooling), sized around 1200px on its long edge
before downsampling for the embed. Text boxes need an explicit
`width`, not `left`+`right`. Always seed with a `canvas.json` whose
artboard entry is `{"file": "Main.dc.html", "x": 0, "y": 0, "w": 1200,
"h": 627}` — omitting it can leave the frame narrower than the actual
design and clip the right side.

## Instructions

You are drafting a single LinkedIn post for "Humanity Moment of the Day."

1. **Check the recent run before picking a SOURCE.** Look at the last
   several posts in `posts/` and avoid repeating the same author,
   voice, or genre back to back. In particular, check whether recent
   quotes have skewed toward one gender or background — this project
   draws from poetry, popular music, fiction, biography, art, and
   literature broadly, and the selection should actually reflect that
   range over time, not just in theory.

2. **Lead with the source material.** Present the quote/lyric/passage
   faithfully, with correct attribution (who, what work, and year if known).
   Do not alter wording. If the source is a song lyric or literary excerpt,
   keep it short enough to stand alone as the visual/emotional center of
   the post.

3. **Add 1-3 lines of commentary, credited to "AI for Society Online."**
   This is a short, sincere reflection — not a summary of the quote and not
   a business lesson forced onto it. It should sound like a person noticing
   something true, not a marketer finding an angle. Avoid:
   - Corporate framing ("here's what this teaches us about leadership...")
   - Hashtag-bait sentimentality ("This hit different 😭")
   - Explaining the obvious meaning of the quote line by line
   End the commentary with the attribution line, e.g.:
   `— AI for Society Online`

4. **Describe a suitable accompanying image.** Provide a short image
   direction (1-2 sentences) suitable for pairing with the quote as a
   LinkedIn image post. The image should evoke the mood, not illustrate
   the words literally. Note: actual image generation/sourcing happens in
   a separate step — this prompt only produces the *direction*.

5. **Format for LinkedIn:**
   - Short paragraphs / single-line breaks (LinkedIn collapses long
     unbroken paragraphs and rewards whitespace).
   - No hashtags by default — the tone should read as literary, not
     promotional. Only include one if it is genuinely apt, and never more
     than one or two.
   - Keep total post text under ~900 characters so it doesn't get
     truncated behind "see more" too aggressively.

6. **Draft a personal-profile repost comment.** A short (2-4 sentence)
   comment the user can post from their own personal LinkedIn profile
   when resharing the "AI for Society Online" post — distinct in voice
   from the "AI for Society Online" commentary: first-person, personal,
   understated, not a restatement of the POST TEXT commentary. Good
   material: a genuinely interesting fact about the source or its
   creator that didn't make it into the main commentary (a biographical
   detail, an origin story, something surprising) — self-contained, so
   it reads fine even for someone who hasn't seen the original post yet.

## Output format

Return exactly these sections:

```
SOURCE QUOTE:
<the quote/excerpt, attributed>

IMAGE DIRECTION:
<1-2 sentence description of a suitable accompanying image>

POST TEXT:
<the full LinkedIn post: quote presented, then 1-3 line commentary,
then "— AI for Society Online", then optional hashtags>

REPOST COMMENT:
<2-4 sentence personal-profile repost comment, per step 6>
```
