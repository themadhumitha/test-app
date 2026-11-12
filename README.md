# Quiz CLI

An interactive terminal quiz game for practicing JavaScript, Node.js, and general programming concepts. It runs with Node.js, reads its quiz content from a local JSON file, and uses Node.js built-in modules rather than third-party runtime packages.

## Key Features

- Choose from **JavaScript Basics**, **Node.js Fundamentals**, and **General Programming**. Each category currently contains five questions.
- Play all questions in a category or select a three- or five-question quiz when that option is available.
- Answer numbered multiple-choice prompts; invalid menu selections are rejected and prompted again.
- Questions are shuffled for each quiz session.
- See immediate correctness feedback and explanations, followed by a final score, performance message, and review of incorrect answers.
- Start another quiz from the replay prompt without restarting the program.
- Display styled terminal output with ANSI escape codes; no color library is required.

## Technologies

- **JavaScript** using ECMAScript modules
- **Node.js 18 or later**
- Node.js built-in modules: `node:fs/promises`, `node:path`, `node:url`, and `node:readline`
- ANSI terminal escape codes for text styling

## Prerequisites

- Node.js **18.0.0 or later**
- npm, included with standard Node.js installations, if using the npm commands below

## Installation and Setup

1. Clone the repository and change to the application directory:

   ```bash
   git clone https://github.com/themadhumitha/test-app.git
   cd test-app/test-app
   ```

2. No dependency installation is required. The package manifest declares no third-party dependencies.

## How to Run

From the `test-app/` application directory, start the quiz with either command:

```bash
npm start
```

or:

```bash
node index.js
```

Use the numbered prompts to choose a category, quiz length, and answer. Press Enter when prompted to continue between questions. At the end, respond `y` or `n` to the replay question.

## Dependencies and Scripts

There are **no third-party runtime dependencies** declared in `package.json`. The application uses Node.js built-ins and its local modules.

| Command | Purpose |
| --- | --- |
| `npm start` | Runs `node index.js` to start the quiz. |
| `npm test` | Runs Node.js's built-in test runner with `node --test`. |

No project-specific test files are present in the inspected project structure, so `npm test` does not execute a project test suite.

## Project Structure

```text
test-app/                         # Application directory
├── data/
│   └── questions.json            # Quiz categories and question content
├── src/
│   ├── colors.js                 # ANSI terminal color and style helpers
│   ├── input.js                  # Readline prompts and input handling
│   └── quiz.js                   # Quiz state, question flow, scoring, and results
├── index.js                      # CLI entry point and main game loop
└── package.json                  # Package metadata, scripts, and Node.js requirement
```

At the repository root, `README.md` documents the project. The `__MACOSX/` entries and `.DS_Store` are operating-system metadata, not application source files.

## Question Data

The application loads `data/questions.json` relative to `index.js`. Its top-level `categories` object contains category entries with a display `name` and a `questions` array. Each question uses the following shape:

```json
{
  "question": "Question text",
  "options": ["First option", "Second option"],
  "answer": 0,
  "explanation": "Why the answer is correct."
}
```

`answer` is a **zero-based index** into `options`; the interactive prompts display choices using one-based numbering. The repository currently includes three categories with five questions each. This JSON file is the quiz content source; no separate configuration file is specified.

## Testing

Run the package's test script from the application directory:

```bash
npm test
```

The script invokes `node --test`. No project-specific test files were found in the inspected repository structure.

## API

This project is a local interactive command-line application. No HTTP or other network API is specified.

## Troubleshooting

- **Node.js version or syntax errors:** Check `node --version`; the project requires Node.js 18.0.0 or later.
- **Quiz data fails to load:** Run the command from the `test-app/` directory and verify that `data/questions.json` exists and contains valid JSON.
- **An answer is not accepted:** Enter the one-based option number displayed in the prompt. The `answer` value stored in JSON is zero-based.

## License

`package.json` declares the **MIT** license. A separate license file was not present in the inspected repository structure.
