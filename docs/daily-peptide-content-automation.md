# Lion Elite Wellness — Daily Peptide Content Automation

## Objective
Automate a daily social media education series for Lion Elite Wellness where each day features one peptide/product from lionelitewellness.com.

## Non-Negotiable Brand Rule
Every Lion Elite Wellness peptide/product visual MUST use the approved Lion Elite Wellness vial branding as the canonical visual reference:
- Clear vial
- Gold top cap with silver crimp band
- White / black / gold label design
- Lion Elite Wellness lion logo and wordmark
- Product name on black center band
- Purity / Research Use Only text
- Product strength in gold

Do NOT use generic vials, alternate branding, fabricated labels, or unrelated product packaging.

## Content Format
Create ONE individual image per peptide. Never combine multiple peptide posts into one giant collage or grid.

Recommended format:
- 1:1 square for cross-platform use, or 4:5 portrait for Instagram feed
- Black / gold / white premium Lion Elite aesthetic
- Actual approved Lion Elite vial style shown prominently
- Peptide Info Series title
- Day number
- Peptide/product name
- What it is
- Mechanism/pathway being researched
- Areas of research
- What makes it different
- CTA to lionelitewellness.com
- Research-use-only disclaimer

## Daily Series Workflow
1. Pull the active peptide/product catalog from lionelitewellness.com.
2. Select one product per day, avoiding duplicates until the full catalog has been covered.
3. Generate one individual branded educational image using the approved Lion Elite vial design.
4. Create a concise caption that is educational, engaging, and research-focused.
5. Avoid medical treatment claims, dosage instructions, or guaranteed outcomes.
6. Include research-use-only positioning where appropriate.
7. Save the generated media to a location that provides a stable public HTTPS media URL.
8. Send the public media URL to Metricool.
9. Schedule the post on all compatible connected Lion Elite Wellness social networks.
10. Use Metricool best-time data when the user has not specified a posting time.
11. Record the scheduled product/date so future runs continue with the next peptide.

## Connected Metricool Brand
Brand: Lion Elite Wellness
Metricool brand ID: 6575911
Timezone: America/New_York
Connected networks observed:
- Instagram
- LinkedIn
- TikTok

## Platform Requirements
- Instagram feed posts require media.
- TikTok requires media and may require a title/video depending on post type.
- LinkedIn can accept text-only posts, but the peptide info series should use the branded image whenever possible for consistency.

## Current Media Bottleneck
Generated ChatGPT images and private Canva design/thumbnail URLs are not automatically stable public media URLs for Metricool.

The automation therefore needs a media-hosting step that takes the generated image and returns a stable public HTTPS URL before calling Metricool.

Do not upload private/generated files to random public file-sharing or temporary hosting services. Use an approved business-controlled storage/CDN workflow.

Suggested implementation options for Claude to build:
- Cloudinary
- AWS S3 + CloudFront
- Supabase Storage public bucket
- Vercel Blob
- Existing Lion Elite website/CDN asset storage

The storage provider should return a direct, stable HTTPS image URL accessible by Metricool.

## Automation Logic
Pseudo-flow:

```text
DAILY CRON
  -> get next product in peptide content queue
  -> generate branded image using approved Lion Elite vial reference
  -> generate research-focused caption
  -> upload final image to approved public media storage
  -> receive direct HTTPS image URL
  -> query Metricool best posting time
  -> create scheduled Metricool post with image URL + caption
  -> log product, date, platform, Metricool post ID, and status
  -> move queue pointer to next peptide
```

## Content Queue
Start with the active Lion Elite Wellness catalog. Products previously identified for the educational series include:
- Retatrutide
- Tirzepatide
- AOD-9604
- IGF-1 LR3
- CJC-1295 / Ipamorelin
- Tesamorelin
- BPC-157
- BPC-157 / TB-500
- GHK-Cu
- KLOW
- Semax
- Selank
- SS-31
- NAD+
- MOTS-c
- KPV
- PT-141
- Kisspeptin
- Thymosin Alpha-1
- Epithalon
- Glutathione

Claude should verify the live catalog before finalizing the queue.

## Caption Style
Tone:
- Premium
- Scientific
- Educational
- Direct
- Curiosity-driven
- Short enough to read quickly

Example structure:

```text
PEPTIDE INFO SERIES — DAY 1

RETATRUTIDE

Retatrutide is being researched as a multi-receptor agonist targeting GLP-1, GIP, and glucagon pathways.

Why researchers are paying attention:
• Metabolic signaling
• Energy balance
• Glucose regulation
• Body-composition research

Understanding the mechanism matters more than following the hype.

Explore more research at lionelitewellness.com

For research purposes only. Not for human consumption.
```

## First Post
Day 1: Retatrutide 10 MG

The first individual Retatrutide visual has already been created using the approved Lion Elite vial branding direction. The next engineering task is to automate the stable-public-URL media step so the generated image can be attached and scheduled through Metricool.

## Success Criteria
The system is complete when it can run daily with minimal human intervention and:
- choose the next peptide
- generate one individual branded visual
- use the approved Lion Elite vial design
- generate compliant educational copy
- host the media at a stable public HTTPS URL
- schedule the post through Metricool
- log success/failure
- continue to the next peptide the following day
