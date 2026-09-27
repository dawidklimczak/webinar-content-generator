# Webinar Content Generator

A Streamlit tool that turns a raw webinar recording into a ready-to-publish set of marketing assets — quotes, syllabus, keywords, description, and a formatted Word document.

## Problem

After a webinar is recorded, someone still has to sit through it to pull out the promotional material for it: a marketing description, a program/syllabus, standout quotes, SEO keywords, and a benefits list. That's a repetitive, time-consuming task that has to happen for every recorded session. This tool automates the whole path from audio file to publish-ready copy.

## Solution & Architecture

- **Streamlit** front end for uploading a recording and downloading the result
- **AssemblyAI** for transcription of the raw audio
- **OpenAI** with a strict JSON schema for the response — the model is required to return top quotes, a syllabus (title + description per topic), keywords, a marketing description, and benefit bullets in a fixed, validated shape
- **python-docx** to assemble the structured output into a formatted Word document with proper styling, ready to hand off or publish directly

## Key Product Decisions

- **Structured output over free text**: rather than asking the model for a blob of marketing copy and parsing it afterward, the app defines an explicit JSON schema (minimum/maximum item counts, field-level descriptions) so the output is reliably shaped and directly usable by downstream code — no fragile text parsing.
- **Single input, multiple deliverables**: one recording produces several distinct marketing assets in one pass (quotes, syllabus, keywords, description, benefits) instead of requiring separate manual passes for each.
- **Word output as the deliverable**: the result is exported as a formatted `.docx` rather than plain text, matching how the content would actually be handed off to a marketing or content team.

## Outcome

Reduced turning a recorded webinar into usable marketing collateral from a manual transcription-and-writing task to a single upload-and-generate step, with a consistent, structured output every time.

## Preview

<!-- screenshot placeholder — added separately -->

## Note

Source code is kept in a private repository; happy to share on request.
