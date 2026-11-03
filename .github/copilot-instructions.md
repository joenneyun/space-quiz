# Copilot instructions

## Project structure and flow

- The project is a dependency-free static Korean space quiz. The UI, styles, question data, and behavior all live in the root `index.html`.
- The page has three in-place screens: introduction, quiz, and results. The script switches screens with the `.hidden` class; quiz state (`currentQuestion`, `score`, and `answered`) drives rendering, answer feedback, progress, and results.
- Questions are stored in the `questions` array. Each answer is the zero-based index of its matching choice; `renderQuestion()` builds the answer buttons and `selectAnswer()` handles scoring and feedback.

## Build, test, and lint

- There are no package manifests or configured build, test, or lint commands.
- Run the app by opening `index.html` directly in a browser; no server or dependency installation is needed.
- For a manual end-to-end check, start and restart the quiz, answer correctly and incorrectly, advance through all 10 questions, and confirm the progress, score, feedback, and final result update.

## Project conventions

- Keep the app self-contained in `index.html`; do not add a framework, package, or external runtime dependency for a local UI change.
- Keep user-facing copy in Korean and retain `<html lang="ko">`.
- Reuse the CSS custom properties in `:root` for the shared dark-space palette. Keep answer interaction styles on `.answer` and screen state in the existing screen sections rather than introducing a second rendering pattern.
- Preserve the mobile breakpoints and `prefers-reduced-motion` handling when changing layout or animation.
- Preserve semantic buttons, visible keyboard focus, the progress bar's ARIA values, and the live feedback announcement when changing quiz interactions.
