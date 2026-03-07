# test-app (quiz-cli)

High-Level Description
- An interactive command-line quiz game that reads question categories from data/questions.json and runs a timed-free, turn-based quiz in the terminal. It provides category selection, configurable question counts, per-question feedback, a progress bar, and a final results summary.

Features
- Interactive CLI with menu-style selection and yes/no confirmation.
- Category selection driven by data/questions.json (the repo includes a "JavaScript Basics" category).
- Choose number of questions (All / 3 / 5 when available).
- Shuffled questions per run and a visual progress bar while quizzing.
- Per-question feedback, explanations (when available), and a results summary that lists incorrect answers for review.
- Colored terminal output using built-in ANSI codes (no external dependencies).

Project Structure
.
├── data
│   └── questions.json        # Quiz data (categories and questions)
├── index.js                  # CLI entrypoint: loads data and runs main loop
├── package.json              # Project metadata and scripts (start, test); Node >=18
└── src
    ├── colors.js             # ANSI color helpers and small convenience functions
    ├── input.js              # Readline-based input helpers: prompt, select, confirm
    └── quiz.js               # Quiz class: game logic, shuffling, progress bar, results

Getting Started

Prerequisites
- Node.js >= 18.0.0 (package.json "engines" specifies this)
- A POSIX-like terminal or terminal emulator that supports ANSI colors for best experience.

Installation
1. Clone or extract the project and change to the project root.
2. (Optional) Install dependencies. This project uses only Node built-ins; there are no external dependencies listed in package.json:
   - npm install

Run
- Start the CLI:
  - npm start
  - or: node index.js
  - or (on Unix-like systems) make index.js executable and run ./index.js (the file contains a shebang)

Minimal Usage / Workflow
1. Run the app (see commands above).
2. Choose a category from the presented list (categories are read from data/questions.json).
3. Select how many questions to attempt (All / 3 / 5 — options depend on category size).
4. Press Enter to begin.
5. Answer each question by entering the option number shown.
6. Press Enter to continue between questions.
7. At the end you'll see a results summary (score, percentage, motivational message) and a review of incorrect answers.
8. When prompted, choose whether to play again.

Notes
- Questions are read from data/questions.json. The included dataset contains a "JavaScript Basics" category.
- The project is written as ES modules ("type": "module" in package.json).
- There is a "test" npm script that runs `node --test`, but no tests are included in this repository.
