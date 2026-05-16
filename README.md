# quiz-cli

## Project overview

`quiz-cli` is an interactive command-line quiz game for learning JavaScript.

From the repository contents, it is a small Node.js application with:
- a CLI entrypoint in `index.js`
- reusable modules in `src/`
- quiz content stored in `data/questions.json`

The app appears to guide a user through:
- choosing a quiz category
- selecting a question count
- answering questions interactively
- viewing results and reviewing missed answers

## Setup instructions

### Prerequisites
- Node.js `>=18.0.0`

### Install
```bash
npm install
```

### Run
```bash
npm start
```

or run the entrypoint directly:

```bash
node index.js
```

### Configuration and content
- No `.env.example`, `.env.sample`, or runtime environment variables were present in the files reviewed.
- Quiz content is configured in `data/questions.json`.
- The question bank is organized by category and can be edited directly in that file.

### Testing
A test script is defined in `package.json`:

```bash
npm test
```

The script uses Node’s built-in test runner (`node --test`).

## Usage examples

Start the quiz:

```bash
npm start
```

Run the CLI without npm:

```bash
node index.js
```

Run the test command:

```bash
npm test
```

Add or update quiz content:
- edit `data/questions.json`
- each question uses the observed schema:
  - `question`
  - `options`
  - `answer` as a zero-based index
  - `explanation`

## File structure

```text
.
├── index.js
│   Main CLI bootstrap and application flow
├── package.json
│   Project metadata, Node engine requirement, and scripts
├── data/
│   └── questions.json
│       Quiz categories and question bank
└── src/
    ├── colors.js
    │   ANSI terminal styling helpers
    ├── input.js
    │   Readline-based prompt, select, confirm, and pause helpers
    └── quiz.js
        Quiz state, scoring, progress, and results logic
```

## Additional details

- `package.json` declares:
  - `name: "quiz-cli"`
  - `type: "module"`
  - `main: "index.js"`
  - scripts:
    - `start: node index.js`
    - `test: node --test`
- The quiz content file contains these top-level categories:
  - `javascript`
  - `nodejs`
  - `general`
- `src/quiz.js` includes logic for:
  - shuffling questions
  - tracking score and answers
  - rendering a progress bar
  - printing results and review information
- `src/input.js` provides the interactive UX helpers used by the CLI:
  - `createInterface`
  - `select`
  - `confirm`
  - `pressEnter`
- Terminal colors are centralized in `src/colors.js`, including helpers like:
  - `success`
  - `error`
  - `highlight`

Not specified in the repository files reviewed:
- deployment configuration
- environment variables
- CI/workflow files
- a dedicated `README.md` source of usage notes