# AI YouTube Content Engine

A strict, state-based workflow for creating original YouTube content that matches a channel's style.

## Trigger Phrases

ALWAYS use this skill when the user says "let's create a youtube video", "youtube video", "create a video for my channel", "make a youtube script", or any similar phrase about producing YouTube content. Trigger immediately — do not wait for further clarification.

## CORE BEHAVIOR RULES (STRICT)

- Follow states in exact order
- Ask for ONLY ONE input at a time
- STOP after each state and wait for user input before continuing
- DO NOT skip states
- DO NOT reference or think about visuals before STATE 7

## LANGUAGE SELECTION — ALWAYS FIRST

Before anything else, ask:

> "Should this video be created in English or Finnish (Suomeksi)?"

- If Finnish is chosen: ALL outputs — analysis, script, prompts, thumbnails, export — must be written in Finnish
- If English is chosen: continue in English

Then move to STATE 1.

## SYSTEM FLOW

| State | Name |
|-------|------|
| 1 | Channel Link |
| 2 | Transcripts |
| 3 | Topic / Ideas |
| 4 | Channel Analysis |
| 5 | Style DNA Extraction |
| 6 | Script Generation |
| 7 | Visual Input |
| 8 | Visual Style Analysis |
| 9 | Image Prompts |
| 10 | Video Prompts (optional) |
| 11 | Thumbnail Input |
| 12 | Thumbnail Analysis |
| 13 | Thumbnail Generation |
| 14 | Export (optional) |

## STATE 1: CHANNEL LINK

Ask:

> "Please provide the YouTube channel link."

Then STOP.

## STATE 2: TRANSCRIPTS

Ask:

> "Provide 2–3 FULL video transcripts from this channel."

Rules:
- Must be full transcripts — do NOT accept summaries
- Do NOT summarize them yourself

Then STOP.

## STATE 3: TOPIC OR IDEAS

Ask:

> "Do you want me to generate video ideas based on the channel, or do you already have a topic in mind?"

Then STOP.

## STATE 4: CHANNEL ANALYSIS

Analyze the transcripts and extract:

- Niche & target audience
- Hook style
- Script flow structure
- Sentence style (length, complexity)
- Emotional pacing curve
- Retention techniques
- Average words per second

Return as a structured analysis. Then STOP.

## STATE 5: STYLE DNA EXTRACTION

Extract deep writing behavior — not summaries, but HOW it works:

- Sentence rhythm and length variation
- Flow pattern between ideas
- Use of repetition
- Tone (casual, authoritative, energetic, etc.)
- Transition techniques
- Curiosity gaps and open loops
- Emotional triggers
- Direct address ("you", "we", rhetorical questions)
- Level of detail and specificity

Return as a Style DNA profile. Then STOP.

## SCRIPT LENGTH CONTROL

Before writing the script:

- Calculate average word count from the transcripts provided
- Define a TARGET WORD COUNT (±5%)
- Note the pacing (words/sec) to match the channel's delivery speed

## STATE 6: SCRIPT GENERATION (STYLE LOCKED)

Generate a FULL original script. Rules:

**MUST:**
- Match Style DNA exactly
- Match pacing, rhythm, and sentence structure
- Match the emotional flow curve
- Hit the target word count (±5%)

**MUST NOT:**
- Use generic YouTube script structures
- Think about or reference visuals in any way

Before writing: Show the target word count.
After writing: Show the final word count.

Then STOP. Do NOT proceed to visuals until user confirms the script.

## CRITICAL VISUAL GATE

- FORBIDDEN to ask for images before STATE 7
- FORBIDDEN to think about visuals during STATE 6
- FORBIDDEN to reference visual style before it is provided
- Visual processing begins ONLY AFTER script is confirmed complete

## STATE 7: VISUAL INPUT

Ask:

> "Please upload 3–5 sample images from the channel's videos (NOT thumbnails — these should be frames or screenshots from the actual video content)."

Then STOP.

## STATE 8: VISUAL STYLE ANALYSIS

Analyze the uploaded images and extract a VISUAL STYLE PROFILE:

- Art style (realistic, illustrated, cinematic, etc.)
- Color palette (warm/cool, saturated/muted, dominant colors)
- Lighting style (natural, dramatic, flat, studio, etc.)
- Camera style (close-up, wide, POV, overhead, etc.)
- Composition patterns
- Detail level
- Overall mood

DO NOT generate any image prompts yet. This step is strictly analysis.

Then STOP.

## STATE 9: IMAGE PROMPTS (EVERY SCRIPT BEAT)

Generate image prompts for every single script beat.

Rules:
- Each beat = maximum 3–5 seconds of spoken script
- Each prompt must be fully standalone (no references to previous prompts)
- Each prompt must label the exact script segment it covers
- Break large paragraphs into multiple beats as needed
- Do NOT skip any part of the script
- Every prompt must follow the Visual Style Profile from STATE 8 exactly

Format for each beat:

```
[Script Segment]
"<exact text of the script beat>"

Image Prompt: <fully standalone description including subject, environment, lighting, mood, camera angle, and visual style>
Camera Angle: <specific angle>
Lighting: <lighting description>
Mood: <emotional mood>
Action: <what is happening in the frame>
```

Each image prompt MUST fully describe the scene on its own — as if someone reading it had no other context.

Then STOP.

## STATE 10: VIDEO PROMPT OPTION

Ask:

> "Do you want me to generate video motion prompts for each image prompt?"

- If YES → generate a video prompt for every single image prompt (motion, camera movement, duration), then continue
- If NO → skip to STATE 11

Then STOP.

## STATE 11: THUMBNAIL INPUT

Ask:

> "Please upload 2–3 thumbnail images from the channel."

Then STOP.

## STATE 12: THUMBNAIL ANALYSIS

Analyze the uploaded thumbnails and extract:

- Text style (font weight, casing, color, placement)
- Composition layout
- Color contrast approach
- Emotional triggers (facial expression, urgency, curiosity, etc.)
- Common visual patterns

Then STOP.

## STATE 13: THUMBNAIL GENERATION

Generate 5 thumbnail concepts matching the channel's thumbnail style.

For each:
- **Visual concept:** What is shown in the image
- **Text overlay:** Exact text and placement
- **Emotion trigger:** What feeling it creates in the viewer
- **Style-matched prompt:** A detailed image generation prompt following the thumbnail style profile

Then STOP.

## STATE 14: EXPORT (OPTIONAL)

Ask:

> "Do you want me to export everything (topic, script, image prompts, video prompts, thumbnail prompts) into a file? Choose: .docx Word document or .txt plain text."

- If .docx → produce a formatted Word document with clear sections and headings for each component
- If .txt → write a clean plain text file with clearly labeled sections
- If NO → close the session

## FINAL RULES

- NEVER copy or reproduce content from the channel — always stay original
- MATCH style, NOT wording
- FOLLOW the state system strictly — never jump ahead
- If Finnish was selected at the start, ALL text in ALL states is in Finnish
- Each image prompt covers the exact script segment text and is fully self-contained
- Each beat = 3–5 seconds maximum
