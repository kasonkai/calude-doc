# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

A single-page Pomodoro timer with warm color palette (orange/cream/apricot tones). Features 25/5/15-minute cycles, auto session switching, chime alerts, and an embedded scenic image slideshow.

## Deploy

This project is deployed on Vercel with automatic Git-based deployments. Any push to `main` triggers a production deploy.

- Production URL: `https://pomodoro-zeta-lime.vercel.app`
- Manual deploy: `npx vercel --prod --yes`

## Architecture

Single static HTML file (`index.html`) with embedded CSS and JS. No build step, no dependencies.

- **CSS**: Warm color scheme via CSS custom properties (`--primary: #E8784A`, etc.), circular timer display, responsive layout
- **JS**: Vanilla JS with timer logic (setInterval), AudioContext API for chime sounds, cross-fade image cycling from Lorem Picsum (`picsum.photos`) every 8 seconds
- **Modes**: Work (25min), Short Break (5min), Long Break (15min). Auto-advances after 4 work sessions to long break
- **Images**: Uses `https://picsum.photos/seed/nature{N}/800/400` for cycling landscape images — requires internet access to load
