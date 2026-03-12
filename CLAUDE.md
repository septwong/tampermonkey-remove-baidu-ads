# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Tampermonkey userscript that removes distracting elements from Baidu and Bing search pages:
- The "即刻体验百度AI搜" guide element (`#s_new_search_guide`) on Baidu
- Placeholder text in the search input box
- Chat input area placeholders in Baidu AI chat features
- Hot search recommendations (`.sb_form_placeholder`) on Bing

## Commands

No build or test commands needed. This is a plain Tampermonkey userscript:
- Edit [UserScript.js](UserScript.js) directly
- Install in Tampermonkey browser extension for testing
- Deploy to GreasyFork using the `@downloadURL` and `@updateURL` metadata

## Code Architecture

- **Single file**: [UserScript.js](UserScript.js) contains all the logic
- **Pattern**: Uses `MutationObserver` to handle dynamically loaded DOM elements
- **Target URL**: Only runs on `https://www.baidu.com/*`
- **No dependencies**: Pure vanilla JavaScript, no external libraries