# quiz-cli

## Project overview

`quiz-cli` is an interactive command-line quiz game for learning JavaScript and related Node.js fundamentals. It is built as a Node.js **ES module** app and uses only built-in Node APIs, including `readline`, so there are **no external runtime dependencies**.

The quiz flow is simple: choose a category, choose how many questions to answer, respond to multiple-choice questions, review your score and explanations, and optionally play again.

## Features

- Interactive terminal-based quiz experience
- Category selection for:
  - JavaScript
  - Node.js
  - General programming
- Option to choose all questions or a smaller set
- Multiple-choice answers entered by number
- Score summary and performance feedback
- Explanations shown after each question
- Review of incorrect answers at the end
- Replay support for another quiz round
- No third-party dependencies

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

### Key files

- `index.js` — application entry point and main quiz loop
- `src/quiz.js` — quiz logic, scoring, progress, and results
- `src/input.js` — `readline`-based input helpers
- `src/colors.js` — ANSI terminal color helpers
- `data/questions.json` — quiz categories, questions, answers, and explanations

## Requirements

- **Node.js 18.0.0 or newer**

## Installation

Clone the repository and install dependencies:

```bash
npm install
```

> The project does not use external packages, but `npm install` is still a standard way to set up the repository.

## Usage

### Start the quiz

```bash
npm start
```

This runs:

```bash
node index.js
```

### Alternative

```bash
node index.js
```

## Question format

Quiz content is stored in `data/questions.json`. Categories currently include `javascript`, `nodejs`, and `general`.

Each question uses the following structure:

```json
{
  "question": "Question text here",
  "options": ["Option A", "Option B", "Option C", "Option D"],
  "answer": 2,
  "explanation": "Why the correct answer is correct."
}
```

### Notes

- `question` is the prompt shown to the user.
- `options` is the list of possible answers.
- `answer` is the **zero-based index** of the correct option.
- `explanation` is shown after the answer is evaluated.

When adding or editing questions, make sure the `answer` value matches the correct option index.

## Testing note

The repository includes a test script in `package.json`:

```bash
npm test
```

This runs:

```bash
node --test
```

> No test files are currently visible in the repository structure provided, so the command may not run meaningful tests until tests are added.

## Development and contribution

This project is small and easy to extend. Good contribution ideas include:

- Adding new quiz categories
- Expanding the question set
- Improving question shuffling or scoring
- Adding automated tests
- Refining terminal output and UX

When contributing, keep the codebase aligned with its current ES module structure and built-in `readline` approach.

## License

MIT
