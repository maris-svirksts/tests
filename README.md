# quiz-cli

`quiz-cli` is an interactive command-line quiz game for learning JavaScript. It runs in the terminal, lets the player choose a category and question count, then presents questions, tracks score, and shows results at the end.

## Overview

- Node.js ES modules project (`"type": "module"`)
- Entry point: `index.js`
- Quiz data: `data/questions.json`
- Terminal interaction and styling live in `src/`

## Prerequisites

- Node.js `>=18.0.0`

## Install

Install dependencies with npm:

```bash
npm install
```

## Run

Start the interactive quiz:

```bash
npm start
```

This runs:

```bash
node index.js
```

## Test

Run the built-in Node test runner:

```bash
npm test
```

This runs:

```bash
node --test
```

## Configuration

No `.env` file, environment configuration, or external service setup is required. The app reads quiz data from `data/questions.json` at runtime.

## Usage

Typical flow in the terminal:

1. Choose a quiz category.
2. Choose how many questions to answer.
3. Answer each question interactively.
4. Review your score and incorrect answers.
5. Decide whether to play again.

You can also run the entry point directly:

```bash
node index.js
```

## File structure

```text
.
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Key files

- `index.js` — application bootstrap and main quiz loop
- `data/questions.json` — quiz question data source
- `src/input.js` — readline helpers for prompts, selection, confirmation, and pause
- `src/quiz.js` — quiz state, scoring, progress, and results display
- `src/colors.js` — ANSI color/style helpers used for terminal output

## Additional details

- The app uses a `Quiz` class to manage questions, answers, progress, and final scoring.
- Questions are shuffled with a Fisher-Yates implementation in `src/quiz.js`.
- The terminal UI includes styled feedback such as success, warning, error, info, and highlighted text.
- `index.js` clears the console, prints a banner, prompts for category and question count, runs the quiz, then offers a replay prompt.