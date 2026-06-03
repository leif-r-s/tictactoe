# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a single-file Tic Tac Toe game: `tictactoe.html`. It is a self-contained browser application with no build system, dependencies, or package manager.

## Running the App

Open `tictactoe.html` directly in a browser. No server or build step is required.

## Architecture

Everything lives in one HTML file with three sections:

- **CSS** (lines 7–118): Dark-themed UI using CSS Grid for the 3×3 board. Color palette: `#e94560` (X/red), `#53c28b` (O/green), `#1a1a2e`/`#16213e`/`#0f3460` (backgrounds).
- **HTML** (lines 121–148): Static board of 9 `.cell` divs, each with `data-i` index attributes. Score display, status line, and two control buttons.
- **JavaScript** (lines 150–299): Vanilla JS, no frameworks.
  - Game state: `board` (9-element array), `current` (active player), `gameOver`, `vsComputer`, `scores`.
  - `WINS`: hardcoded array of 8 winning index triplets.
  - `minimax()` / `computerMove()`: unbeatable AI using full minimax search (O plays as maximizer, X as minimizer).
  - `place(i)`: central move handler — updates DOM, checks win/draw, triggers computer move if needed.
