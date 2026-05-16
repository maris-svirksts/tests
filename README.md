# quiz-cli

Interactive command-line quiz game for learning JavaScript.

`quiz-cli` is a small Node.js terminal application that runs an interactive multiple-choice quiz. It loads question data from `data/questions.json`, lets the user choose a category and question count, asks questions one by one, tracks score and progress, and shows results with answer explanations at the end.

## Features

- Node.js ES modules
- `readline`-based terminal input
- ANSI terminal styling helpers for colored output
- Category selection and configurable question count
- Score tracking, progress display, and final results review
- Replay prompt after each quiz session

## Requirements

- Node.js 18 or newer (`package.json` specifies `node >=18.0.0`)
- npm (or another Node package manager)

## Installation

```bash
git clone <repository-url>
cd quiz-cli
npm install
```

## Running the app

Start the quiz:

```bash
npm start
```

This runs:

```bash
node index.js
```

## Tests

Run the Node test runner:

```bash
npm test
```

## Configuration

No environment variables, `.env` files, or external services are required.

Quiz content is configured in:

- `data/questions.json`

Each question includes:

- `question`
- `options`
- `answer` index
- `explanation`

### Example structure

```json
{
  "categories": {
    "javascript": {
      "name": "JavaScript",
      "questions": [
        {
          "question": "…",
          "options": ["…", "…", "…", "…"],
          "answer": 0,
          "explanation": "…"
        }
      ]
    }
  }
}
```

## Usage

### Start the quiz

```bash
npm start
```

### Run tests

```bash
npm test
```

### Typical quiz flow

1. Displays a banner
2. Prompts you to choose a category
3. Prompts you to choose a question count
4. Asks each question in sequence
5. Shows progress and the final score
6. Displays explanations for the answers
7. Asks whether you want to play again

## Project structure

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

- `index.js` — application entrypoint and main control flow
- `src/quiz.js` — quiz logic, scoring, progress, and results
- `src/input.js` — terminal prompt/select/confirm helpers
- `src/colors.js` — ANSI styling helpers for terminal output
- `data/questions.json` — quiz categories and question data

## Core behavior

The main loop:

- reads the quiz dataset from `data/questions.json`
- creates a `Quiz` instance
- asks questions until completion
- prints results and an answer review
- optionally restarts the game

## Quiz logic

The `Quiz` class in `src/quiz.js` tracks:

- `currentIndex`
- `score`
- `answers`

It also provides:

- `currentQuestion`
- `totalQuestions`
- `isComplete`
- `progress`

And methods for:

- asking the next question
- rendering a progress bar
- showing final results

## Terminal interaction

`src/input.js` provides reusable helpers built on Node’s `readline` interface:

- `createInterface()`
- `prompt(...)`
- `select(...)`
- `confirm(...)`
- `pressEnter(...)`

## Styling

`src/colors.js` exposes helpers like:

- `red`, `green`, `yellow`, `blue`, `cyan`, `magenta`
- `bold`, `dim`
- `success`, `error`, `warning`, `info`, `highlight`

These are used to format CLI output consistently.

## Notes

- No README, CI workflow, or dedicated test files were present in the repository listing.
- No external configuration or secrets handling was observed in-repo.
