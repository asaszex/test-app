# quiz-cli

A lightweight interactive command-line quiz application implemented in Node.js. It runs quizzes from a local JSON question bank (grouped by category), presents multiple-choice questions, tracks score and answers, and shows a final summary with optional explanations.

[![Node >=18](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Test: node --test](https://img.shields.io/badge/test-node__--test-lightgrey)](https://www.nodejs.org/en/)

## Features

- Interactive CLI quiz runner with prompts and selection menus.
- Multiple categories of questions (e.g. javascript, nodejs, general) loaded from a local JSON file.
- Multiple-choice questions with progress display and per-question tracking.
- Score tracking and final results with optional explanations.
- No external dependencies — implemented with built-in Node APIs (ES modules, readline, fs/promises).

## Project Structure

A high-level view of the main files and their responsibilities:

- package.json — project metadata, scripts (`npm start`, `npm test`), Node engine requirement (>=18.0.0), MIT license.
- index.js — main CLI entry point (shebanged, ES module imports), loads data/questions.json and runs the main application loop.
- src/
  - input.js — readline-based input helpers: createInterface(), prompt(), select(), confirm(), pressEnter().
  - quiz.js — Quiz class: shuffle(), askQuestion(), renderProgressBar(), showResults(), tracks score and answers.
  - colors.js — ANSI color utilities for styling CLI output.
- data/questions.json — question bank grouped by category. Each question contains: question, options (array), answer (index), optional explanation.

## Getting Started

Prerequisites
- Node.js >= 18.0.0 (package.json specifies engines.node ">=18.0.0")
- No external dependencies are required.

Installation
1. Clone the repository:
   git clone https://github.com/asaszex/test-app.git
   cd test-app

2. (Optional) Install dependencies:
   This project has no external dependencies, so `npm install` is optional. Running it is harmless:
   npm install

Running the app
- Start the quiz locally:
  npm start
  or
  node index.js

Notes:
- index.js is an ES module that uses built-in Node APIs (fs/promises, readline helpers in src/input.js).
- The script includes a shebang, so on Unix-like systems you can make it executable and run it directly:
  chmod +x index.js
  ./index.js

## Usage / Interactive Flow

When you run the app it will guide you through an interactive sequence (examples below are illustrative of the expected flow; exact prompts may vary slightly):

1. Select a category (e.g., javascript, nodejs, general)
2. Choose the number of questions to attempt (e.g., 5)
3. The quiz runs question-by-question:
   - Each question displays the question text and multiple choice options
   - You enter your choice (e.g., option number or letter depending on prompt)
   - Progress is shown (a progress bar or count)
4. After finishing, you see:
   - Final score (correct / total)
   - Summary of answers and explanations where available
   - Option to retry or exit

Sample session (brief)
- Run:
  npm start

- Example prompts and responses (illustrative):
  Welcome to quiz-cli!
  Select a category:
  > javascript
  How many questions would you like? (max available: 10)
  > 5

  Question 1/5:
  What does X do?
  1) Option A
  2) Option B
  3) Option C
  Your answer: 2
  Correct!

  [Progress: ▓▓▓░░  2/5]

  ... (questions 2–5) ...

  Quiz complete!
  Score: 4 / 5 (80%)
  Review:
  1) Question text — Your answer: B — Correct — Explanation: ...
  2) Question text — Your answer: A — Incorrect — Correct answer: C — Explanation: ...
  Press Enter to exit.

## Testing

- Run the test script defined in package.json:
  npm test
- The test script executes `node --test`. If there are any built-in tests in the repository they will be executed by Node's test runner.

## Contributing

Contributions are welcome. Suggestions:
- Open an issue for feature requests or bug reports.
- Submit pull requests that include clear descriptions and small focused changes.
- Keep code compatible with Node >= 18 and prefer using built-in APIs (no new runtime dependencies unless necessary).

## License

This project is licensed under the MIT License. See the LICENSE file for details.
