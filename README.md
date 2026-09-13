# BookPilot

BookPilot is a free, browser-based AI book recommendation agent. It helps readers find their next book using a local open-source language model, real catalogue data, and a private reading profile.

## What it does

- interprets a natural-language request such as “a cosy fantasy for a weekend”;
- searches Open Library for real books and metadata;
- filters and ranks candidates against the reader profile and reading history;
- stores preferences and the reading list only in the browser;
- optionally runs **Qwen2.5-1.5B-Instruct** locally in the browser through WebLLM for AI-generated explanations.

## Privacy and cost

No API key, account, or paid model is required. When a visitor enables AI, their browser downloads the quantized open-source model and runs it locally. The profile is stored in `localStorage` on that device.

## Agent loop

1. Parse the request and constraints.
2. Call the Open Library search tool.
3. Read the local profile and remove already read or unwanted candidates.
4. Rank books by request fit, genres, length, and history.
5. Use the local LLM to create concise explanations from the returned facts.
6. Save feedback so the next selection is more personal.

## Run locally

This is a static site. Serve the `dist/` directory with any static server, then open it in Chrome or Edge. WebGPU support is recommended for the optional AI mode.

## Stack

Vanilla JavaScript, WebLLM, Qwen2.5-1.5B-Instruct, Open Library API, and browser local storage.
