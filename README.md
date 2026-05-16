# Quiz CLI

An interactive command-line quiz game for learning JavaScript and general programming concepts.

## Features

- Interactive terminal UI with colored output
- Multiple quiz categories
- Choose how many questions to answer
- Randomized question order
- Score summary and progress display
- Review of incorrect answers at the end
- Built with Node.js ES modules and no external dependencies

## Requirements

- Node.js 18 or newer

## Getting Started

### 1. Install dependencies

This project does not use external packages, but you can still install the local project metadata if desired:

```bash
npm install
```

### 2. Run the quiz

```bash
npm start
```

Or run it directly:

```bash
node index.js
```

## How It Works

1. Start the app from the terminal.
2. Choose a quiz category.
3. Choose the number of questions to answer.
4. Answer each multiple-choice question.
5. View your final score and review any incorrect answers.

## Project Structure

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

## Files

- `index.js` - application entry point and main game loop
- `src/quiz.js` - quiz logic, scoring, progress, and results
- `src/input.js` - terminal input helpers
- `src/colors.js` - ANSI color helpers for terminal output
- `data/questions.json` - quiz question data

## Scripts

- `npm start` - run the quiz
- `npm test` - run Node.js tests

## Notes

- The quiz uses built-in Node.js modules only.
- Questions are loaded from `data/questions.json`.
- Answers are entered by choosing the number shown in the terminal.
