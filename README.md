# Quiz CLI

## Description

Quiz CLI is a local, interactive programming quiz application built with Node.js. It loads questions from a JSON file, lets you choose a quiz category and question count, and presents the quiz in the terminal. At the end, it shows your score and reviews incorrect answers with explanations. You can also choose to replay.

## Features

- Choose from JavaScript Basics, Node.js Fundamentals, and General Programming.
- Select how many questions to answer.
- Shuffle questions using a Fisher–Yates shuffle.
- Track quiz progress and score.
- Review incorrect answers and their explanations after the quiz.
- Replay the quiz.
- Use terminal prompts and ANSI colors without third-party packages.

## Technologies

| Technology | Use |
|---|---|
| JavaScript ES modules | Application code |
| Node.js (version 18 or later) | Runtime |
| JSON | Quiz question data |
| `node:readline` | Interactive terminal input |
| `node:fs/promises`, `node:path`, `node:url` | Built-in file and path handling |
| ANSI escape codes | Terminal colors |

## Project Structure

```text
repository/
├── __MACOSX/                 # Metadata artifacts; not application modules
├── .DS_Store                 # Finder metadata artifact
└── test-app/
    ├── package.json          # Package metadata and npm scripts
    ├── index.js              # Application entry point
    ├── data/
    │   └── questions.json    # Quiz categories and questions
    └── src/
        ├── colors.js         # ANSI terminal color helpers
        ├── input.js          # Readline-based input handling
        └── quiz.js           # Quiz flow, scoring, and answer review
```

The application entry point is `test-app/index.js`. It loads `data/questions.json` relative to the module and coordinates the prompts, quiz, and replay flow. The quiz logic is in `src/quiz.js`; terminal input and colors are handled by `src/input.js` and `src/colors.js`.

## Prerequisites

- Node.js 18 or later
- npm, included with Node.js

## Setup and Installation

Run commands from the `test-app` directory:

```sh
cd test-app
```

The project has no third-party dependencies, so no package installation is required to run it.

## Running the Application

From `test-app`, start the quiz with either command:

```sh
npm start
```

```sh
node index.js
```

Follow the terminal prompts to choose a category and question count, answer the questions, and view your results. The application also offers a replay flow.

## Dependencies

There are no third-party runtime dependencies. The application uses Node.js built-in modules:

- `node:fs/promises`
- `node:path`
- `node:url`
- `node:readline`

## Question Data

Questions are stored in `data/questions.json`. The dataset contains five questions in each of these categories:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

Each question includes question text, answer options, a zero-based index identifying the correct answer, and an explanation.

## Testing

Run the configured test command from `test-app`:

```sh
npm test
```

This invokes `node --test`. No project-specific test files are present in the repository analysis.

## Configuration

Package metadata identifies the application as `quiz-cli` version `1.0.0`, uses ES modules, and requires Node.js 18 or later. The package scripts provide the start and test commands. Quiz content is stored in `data/questions.json`.

## API Documentation

This is a local command-line application; no API is specified.

## License

MIT.
