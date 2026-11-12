# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts. The application code and its `package.json` are in the repository's `test-app/` directory. It is written in JavaScript using Node.js ES modules and built-in APIs only; the bundled question bank contains 15 questions across three categories.

## Features

- Choose among JavaScript Basics, Node.js Fundamentals, and General Programming categories.
- Run all questions in a category or choose 3 or 5 questions when available.
- Questions are shuffled for each quiz session.
- Receive immediate answer feedback and explanations, plus a final score and review of incorrect answers.
- Replay without restarting the program.
- Uses ANSI terminal colors without external dependencies.
- Shows a progress bar, final score and performance message, and a review of incorrect answers with the selected and correct choices.

## Technologies

- JavaScript (ECMAScript modules)
- Node.js built-in modules: `node:fs/promises`, `node:path`, `node:url`, and `node:readline`
- No third-party runtime dependencies are declared. The quiz uses Node.js built-ins (`node:fs/promises`, `node:path`, `node:url`, and `node:readline`) and local application modules.

## Dependencies

There are no third-party packages to install. `package.json` specifies Node.js `>=18.0.0`. npm is only needed if you want to use the package scripts (`npm start` and `npm test`); npm is distributed with Node.js.

## Prerequisites

- Node.js 18.0.0 or later
- npm (distributed with Node.js) for the documented npm commands

## Installation and Setup

1. Clone the repository and enter the application directory:

   ```bash
   git clone <repository-url>
   cd <repository-directory>/test-app
   ```

2. No dependency installation is needed; `package.json` declares no external dependencies.

## Usage

Start the interactive quiz from the `test-app` directory:

```bash
npm start
```

Alternatively, run its entry point directly:

```bash
node index.js
```

Choose a category and question count using the numbered prompts. Enter the displayed number for each answer, press Enter when prompted to continue, and answer `y` or `n` when asked whether to play again.

## Project Structure

```text
test-app/
├── data/
│   └── questions.json   # Three categories with questions, options, answers, and explanations
├── src/
│   ├── colors.js        # ANSI terminal color helpers
│   ├── input.js         # Readline prompts, option selection, and confirmation
│   └── quiz.js          # Shuffling, quiz state, scoring, progress, and results
├── index.js             # Entry point, question loading, and main/replay loop
└── package.json         # Package metadata, scripts, and Node.js requirement
```

The repository root also contains this README. `__MACOSX` entries and `.DS_Store` files are archive/OS metadata, not application modules.

## Configuration and Question Data

Quiz content is loaded from `data/questions.json` relative to `index.js`. The top-level `categories` object contains category entries. Each category has a display `name` and a `questions` array; each question uses this shape:

```json
{
  "question": "Question text",
  "options": ["First option", "Second option"],
  "answer": 0,
  "explanation": "Why the answer is correct."
}
```

`answer` is a zero-based index into `options`. The example describes the data structure; existing questions are in `data/questions.json`.

## Testing

The package defines a test script using Node's built-in test runner:

```bash
npm test
```

No test files are present in the repository structure, so this command currently runs the test runner without project-specific tests.

## API Documentation

This project is a local interactive CLI and does not expose an HTTP or other network API.

## Troubleshooting

- **Node.js version error or unsupported syntax:** Verify that `node --version` reports `v18.0.0` or later.
- **Questions fail to load:** Run the application from the repository's `test-app` directory and confirm `data/questions.json` exists and contains valid JSON.
- **Unexpected answer selection:** Enter the option number shown in the prompt; selections are one-based in the CLI even though answers in the JSON data are zero-based.

## License

The package metadata declares the MIT license. A separate license file was not present in the inspected repository files; consult the repository owner for the applicable license text.
