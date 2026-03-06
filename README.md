# Quiz CLI

Interactive command-line quiz game for learning programming topics (JavaScript, Node.js, and general programming).

## About

This repository contains a small, dependency-free CLI quiz application implemented with modern Node.js features (ES modules, async/await). The app is driven by a JSON file of question categories and provides an interactive experience in the terminal: choose a category, select the number of questions, answer prompts, and review results.

## Requirements

- Node.js >= 18.0.0 (see package.json "engines")
- No external dependencies — uses only built-in Node.js modules

## Installation

1. Clone the repository and switch to the project directory.
2. Install Node.js (if not installed) matching the required version.

Optional: initialize a local package install if you plan to extend the project, but no npm packages are required to run.

## Usage

From the project root (run in the `docs` branch or `main` branch):

- Start the CLI using npm:

  npm start

- Or run directly with Node:

  node index.js

The CLI will prompt you to select a category and how many questions to answer. Follow the on-screen prompts to play.

There is also a test script defined in package.json (runs Node's built-in test runner):

  npm test

## Features

- Multiple categories (configured in data/questions.json)
- Choose number of questions (All / 3 / 5 where available)
- Progress bar and per-question feedback
- Final score summary with review of incorrect answers
- Colorized terminal output using ANSI escape codes (src/colors.js)

## Project Structure

- index.js - Entry point and main application loop
- package.json - Project metadata, scripts, and engine requirements
- data/questions.json - Question categories and items used by the quiz
- src/
  - input.js - Prompting and input utilities
  - quiz.js - Quiz class and game logic
  - colors.js - Lightweight terminal color helpers

## Adding or Editing Questions

Questions are stored in data/questions.json. The top-level "categories" object maps category IDs to category objects with a "name" and a "questions" array. Each question object contains:

- question: string
- options: array of strings
- answer: index (number) of the correct option (0-based)
- explanation: optional string shown after answering

Edit or add categories/questions directly in data/questions.json and run the CLI to use them.

## Development notes

- The project uses ES modules ("type": "module" in package.json).
- The code relies only on built-in Node.js modules (fs, readline, path, url).
- Entry point reads data/questions.json relative to index.js using import.meta.url.

## License

This project is licensed under the MIT License (see package.json).
