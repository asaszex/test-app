# Quiz CLI

An interactive command-line quiz game for learning JavaScript and general programming concepts.

This repository contains a small Node.js CLI application that presents multiple-choice questions grouped by category and tracks your score.

## Project overview

- Entry point: `index.js` (ES module)
- Core modules: `src/quiz.js`, `src/input.js`, `src/colors.js`
- Questions data: `data/questions.json`
- Package manifest: `package.json`

## Requirements

- Node.js >= 18.0.0 (the package.json specifies `engines.node: ">=18.0.0"`).

## Install

Clone the repository and (optionally) install dependencies:

```bash
git clone <repo-url>
cd test-app
npm install
```

Note: The project uses only built-in Node.js modules in the source; there may be no external dependencies.

## Run

Start the CLI using the npm script or directly with Node:

```bash
npm start
# or
node index.js
```

When the program runs it will:
- Show a category selection menu (JavaScript Basics, Node.js Fundamentals, General Programming)
- Let you choose how many questions to answer
- Present multiple-choice questions and record your answers
- Show a final score and review incorrect answers

Controls are text-based: select options by entering the number shown, and answer yes/no prompts with `y` or `n`.

## Project structure

Files and folders in the repository's main branch:

- index.js — application entry point (loads questions, runs interactive loop)
- package.json — project manifest (name: `quiz-cli`, node engine requirement, scripts)
- data/questions.json — question categories and question objects (question, options, answer index, explanation)
- src/
  - colors.js — small utility to format colored terminal output using ANSI codes
  - input.js — readline-based helpers for prompting, selecting, and confirming
  - quiz.js — Quiz class implementing game logic, progress, scoring, and results

## Contributing

Contributions are welcome. Suggested improvements include adding more questions, new categories, or improving the user interface.

If you make changes, run the app locally to verify behavior and consider opening a pull request describing your changes.

## License

MIT (as indicated in package.json)

---

(Generated README for the repository.)
