---
version: alpha
name: plain-language
description: "Rewrite or audit prose into plain language: short clear sentences at a 6th-8th grade reading level, one idea per sentence, plain word swaps, and AI-slop cleanup. Use when a draft sounds AI-written, is padded or hard to follow, or when the user says simplify, tighten, make it plain, or plain language. Two modes: edit (default) returns a rewrite; detect audits without rewriting."
metadata: {includeInPrompt: true}
omitted:
  - colors
  - typography
  - spacing
  - rounded
words:
  utilize: use
  leverage: use
  facilitate: help
  enable: let
  streamline: simplify
  commence: start
  demonstrate: show
  illustrate: show
  individuals: people
  robust: strong
  comprises: includes
  encompasses: includes
  "in order to": to
  "due to the fact that": because
  "a number of": some
  "prior to": before
  "subsequent to": after
  "in the event that": if
  "pursuant to": under
  "it is important to note that": delete
banned:
  - delve
  - tapestry
  - realm
  - beacon
  - multifaceted
  - intricate
  - paramount
  - transformative
  - embark
  - supercharge
  - harness
  - ever-evolving
  - game changer
  - paradigm shift
  - cutting-edge
sentences:
  target:
    readingLevel: grade 6-8
    avgWords: 15
  standard:
    maxWords: 20
    maxIdeas: 1
    voice: active
  lead:
    maxWords: 25
    maxIdeas: 1
    voice: active
  short:
    maxWords: 10
    maxIdeas: 1
    voice: active
blocks:
  paragraph:
    maxSentences: 4
    gapAfter: 1 blank line
  listItem:
    maxWords: 25
    gapAfter: 1 blank line
  oneIdeaPerLine: true
components:
  lead:
    typography: "standard sentence: max 25 words, one idea, active voice"
    padding: "1 blank line after"
  step-list:
    typography: "standard sentence: max 20 words, one idea, active voice"
    padding: "1 blank line after"
  definition:
    typography: "standard sentence: name the term, define it in plain words"
    padding: "1 blank line after"
  summary:
    typography: "short sentence: max 10 words, one idea"
    padding: "1 blank line after"
  report:
    typography: "standard sentence: max 20 words, one idea, active voice"
    padding: "1 blank line after"
---

<!-- Adapted in structure from the DESIGN.md spec (https://github.com/google-labs-code/design.md, alpha).
     Method adapted from marketingskills/plain-language-editor (MIT) and wcygan/agent-skills plain-language-rewrite (MIT).
     Writing rules follow ASAN's "One Idea Per Line" guide (6th-8th grade plain language). -->

# Plain Language

## Overview

Plain Language is a writing system for turning hard-to-follow prose into clear writing. The reader is smart but not an expert. They read each sentence once and will not look words up. If a sentence does not land the first time, they stop reading. The benchmark is Richard Feynman explaining a hard idea: the simplest words that still carry the full meaning.

The method is spine-first. Before editing a single sentence, find the one main point and the 3-5 points that hold it up. Then cut to it. Drafts are routinely two to four times longer than they need to be, so assume half or a quarter of the current length. Length is not depth.

Protect the writer's real voice: their vocabulary, bluntness, humor, and uncertainty. Make the minimum edit that fixes the problem. A rough draft should still sound like its author.

Two modes. **Edit** (default): the user shares a draft, you return the rewrite. **Detect**: the user asks whether a piece is readable or asks for an audit without a rewrite; name each pattern you find, quote the line, give the fix in a few words, and stop.

Never add facts, advice, or examples the source does not support. Keep names, dates, numbers, units, code, commands, file paths, and link targets unchanged. Keep a statement uncertain when the source is uncertain. If a sentence is so broken you cannot tell what it meant, do not guess a meaning into it. Mark it and ask the author.

## Typography

Sentences are the type system of writing. Every sentence follows {sentences.standard}: at most 20 words, one idea, active voice. The running target is {sentences.target}: grade 6-8 reading level, about 15 words per sentence on average.

- One idea per sentence. If a sentence carries more than one "and", "which", or "that" clause, split it.
- Active voice. "We checked the papers," not "the papers were checked."
- Every sentence needs a clear who and a clear does-what. Ask: who is the actor, what is the action, what is it done to? If you cannot answer, rewrite the sentence.
- Point first, qualification second. "The figure didn't move. That surprised us."
- Define the jargon or delete it. The first use of a technical term gets a plain definition in the same sentence (see {components.definition}). Never leave a term floating.
- Read each sentence aloud. If you stumble, the reader stumbles. Rewrite until it flows in one pass.
- Never use em dashes. Split into two sentences, or use a comma, parentheses, or a colon for a list.
- Name the subject instead of pointing at it. If "they", "it", or "this" could point at two things, write the noun again.
- Skip figures of speech (metaphor, sarcasm, idiom) unless you say what they mean. "Hard to steer" is fine when you add that it means hard to focus.
- Bold the first use of a term you define. If a document defines several terms, add a short "Words to know" list at the front.
- Give the reader the background they need. If the point needs a concept the reader might not know, add one plain line of context first. Going back moves the piece forward.
- Replace heavy words with their {words} swaps. Delete {banned} words outright. The full swap table lives in references/word-swaps.md.
- Vary sentence length so it does not sound robotic. A short sentence after two medium ones gives the reader a breath.

## Layout

Paragraphs and lists carry the page the way spacing carries a screen.

- One idea per line in chat and instructions: a short sentence, then a blank line before the next idea.
- Paragraphs hold at most 4 sentences ({blocks.paragraph}), then a blank line.
- Lists hold steps or parallel items. Each item is one sentence ({blocks.listItem}).
- Repeat the main point when the topic changes. One short restatement at each section start beats one recap at the end.
- Numbered lists are only for steps and sequences. Parallel items get bullets.
- Headings state findings, never announce them. Write "Most papers blame data," not "The headline finding."
- Kill meta-comments: the text talking about itself ("Here is an overview of...", "Why it matters:"). Delete the frame, keep the point.
- Open with the {components.lead} sentence. Supporting points follow.

## Components

- **lead:** The opening sentence. Follows {sentences.lead}. States the main point with no throat-clearing ("Here's the thing", "Let me be clear").
- **step-list:** Numbered steps for anything the reader must do. Each step is one sentence and one action, following {sentences.standard}.
- **definition:** Name a technical term, then define it in plain words in the same sentence. Delete the term if no plain definition is possible.
- **summary:** 3-5 dot points, main point first. Follows {sentences.short}.
- **report:** The audit output for an edit, in this order: the spine (one sentence on the main point, then 3-5 dot points), the length call, the rewrite, claims to check, contradictions found, what was cut. For detect mode, skip the rewrite and report each pattern with a quoted line and a short fix instead.

## Do's and Don'ts

- Do find the spine before editing a single sentence. If there is no spine, say so.
- Do cut hard. Assume half or a quarter of the length.
- Do check the reading level after the rewrite. Average the scores from two or three checkers. Leave defined terms out of the check. Aim for grade 6-8.
- Do keep the writer's real voice. Minimum effective edit.
- Do list every claim you could not verify as a question for the author. Do not smooth over overclaims ("experts agree", "studies show") or numbers with no anchor.
- Do surface contradictions instead of silently picking one side.
- Don't guess a meaning into a broken sentence. Mark it and ask.
- Don't add facts the source does not support.
- Don't flatten everything into one tidy rhythm.
- Don't use em dashes, colon reveals ("The best part: it learns"), binary contrasts ("It's not X, it's Y"), or fake-profound closing lines. The full pattern catalog is in references/ai-slop-patterns.md.
- Don't use metaphor, sarcasm, or idiom without saying what it means.
- Don't end with a summary-recap paragraph ("In conclusion..."). End on the last concrete point or next action.
