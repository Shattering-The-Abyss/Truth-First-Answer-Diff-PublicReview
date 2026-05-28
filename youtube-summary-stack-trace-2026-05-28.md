# Stack Trace: YouTube Summary Case

Date: 2026-05-28

## Input

User asked for a summary of a YouTube video:

- https://www.youtube.com/watch?v=FjWY1-gZ0Cs

## Attempted Source Path

1. Opened the YouTube page.
2. The page did not expose useful transcript content through the available browsing view.
3. Attempted local transcript extraction with `yt-dlp`.
4. `yt-dlp` was not installed in the local environment.
5. Searched the public web for transcript/summary references.
6. Found accessible public secondary sources.

## Source Quality Classification

| Source | Role | Limitation |
|---|---|---|
| YouTube page | Primary video URL | Transcript not directly accessible in this environment |
| Recall summary | Public AI summary based on transcript | Secondary summary, not raw transcript |
| Acquirer's Multiple article | Public article recap | Secondary editorial/article source |

## Decision

Produce a bounded summary with explicit caveat.

Do not claim to have watched the video.

Do not claim access to the raw transcript.

Do not turn the answer into investment advice.

## Generic Failure Mode

The generic response stops after transcript access fails:

```text
I cannot reliably access the content. Please provide the transcript.
```

This protects against hallucination but under-delivers when public alternatives exist.

## Mission-Driven Pattern

```text
preferred source unavailable
-> preserve boundary
-> search alternate public sources
-> classify source quality
-> answer with caveat
-> keep output useful and bounded
```

## Product Lesson

The assistant did not need more raw capability.

It needed a better operating frame:

- mission
- source hierarchy
- truth boundary
- recipient context
- useful output shape
- stop condition

## Public Safety

This artifact avoids:

- private context
- internal repo references beyond the public case
- hidden prompts
- financial advice
- false transcript claims

