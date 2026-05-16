# quiz-cli

`quiz-cli` is an interactive command-line quiz game for learning JavaScript and related programming topics.

## Overview

This project is a lightweight Node.js CLI app that lets you:

- choose a quiz category
- answer multiple-choice questions in the terminal
- review your score and incorrect answers
- replay with a new randomized question order

## Requirements

- Node.js 18.0.0 or newer
- npm

## Setup

1. Clone the repository.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the quiz:

   ```bash
   npm start
   ```

## Testing

Run the test suite with:

```bash
npm test
```

## Scripts

- `npm start` runs `node index.js`
- `npm test` runs `node --test`

## Project structure

```text
.
├── package.json          # Project metadata, Node engine, npm scripts, entrypoint
├── index.js              # CLI bootstrap and top-level game flow
├── data/
│   └── questions.json    # Quiz categories, questions, answers, explanations
└── src/
    ├── colors.js         # ANSI terminal styling helpers
    ├── input.js          # Readline-based prompt/select/confirm helpers
    └── quiz.js           # Quiz engine, scoring, progress, results
```

## Quiz content

Quiz questions are stored in `data/questions.json`. The current content includes categories for:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

To extend the quiz, edit `data/questions.json` and add or update questions using the existing schema:

- `question`
- `options`
- `answer` (index)
- `explanation`

## Notes

- The app starts from `index.js`.
- Quiz logic lives in `src/quiz.js`.
- Terminal input is handled in `src/input.js`.
- Terminal styling is handled in `src/colors.js`.
