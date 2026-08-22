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

## Instructions

You are drafting a single LinkedIn post for "Humanity Moment of the Day."

1. **Lead with the source material.** Present the quote/lyric/passage
   faithfully, with correct attribution (who, what work, and year if known).
   Do not alter wording. If the source is a song lyric or literary excerpt,
   keep it short enough to stand alone as the visual/emotional center of
   the post.

2. **Add 1-3 lines of commentary, credited to "AI for Society Online."**
   This is a short, sincere reflection — not a summary of the quote and not
   a business lesson forced onto it. It should sound like a person noticing
   something true, not a marketer finding an angle. Avoid:
   - Corporate framing ("here's what this teaches us about leadership...")
   - Hashtag-bait sentimentality ("This hit different 😭")
   - Explaining the obvious meaning of the quote line by line
   End the commentary with the attribution line, e.g.:
   `— AI for Society Online`

3. **Describe a suitable accompanying image.** Provide a short image
   direction (1-2 sentences) suitable for pairing with the quote as a
   LinkedIn image post. The image should evoke the mood, not illustrate
   the words literally. Note: actual image generation/sourcing happens in
   a separate step — this prompt only produces the *direction*.

4. **Format for LinkedIn:**
   - Short paragraphs / single-line breaks (LinkedIn collapses long
     unbroken paragraphs and rewards whitespace).
   - No hashtags by default — the tone should read as literary, not
     promotional. Only include one if it is genuinely apt, and never more
     than one or two.
   - Keep total post text under ~900 characters so it doesn't get
     truncated behind "see more" too aggressively.

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
```
