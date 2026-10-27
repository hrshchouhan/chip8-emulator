# Contributing to CHIP-8 Emulator

Thanks for your interest in contributing! This is a beginner-friendly project: a CHIP-8 emulator written in C++17. All skill levels are welcome, and good first issues are labelled `good first issue`.

## Ways to contribute

- Fix bugs or pick up an open issue
- Improve documentation
- Test on other platforms (Linux and Windows are untested)
- Report bugs with the ROM that triggered them

## Getting started

### Prerequisites

- A C++17 compiler (clang or g++)
- CMake 3.10+
- SDL2

**macOS (tested):**
```bash
brew install cmake sdl2
```

**Linux (untested, help wanted):**
```bash
sudo apt install build-essential cmake libsdl2-dev
```

### Fork, clone and build

1. Fork this repository on GitHub
2. Clone your fork:
```bash
git clone https://github.com/<your-username>/chip8-emulator.git
cd chip8-emulator
```
3. Build:
```bash
mkdir build && cd build
cmake ..
cmake --build .
```
4. Run:
```bash
./chip8-emulator 10 3 ../roms/pong.ch8
```
Arguments: `<Scale> <Delay in ms> <ROM path>`

## Project structure

```
src/chip8.h / chip8.cpp      CPU core: memory, registers, 34 opcode handlers, dispatch tables
src/Platform.h / .cpp        SDL2 layer: window, rendering, keyboard input
src/main.cpp                 Argument parsing and the main loop
roms/                        Test ROMs
```

## Picking and claiming an issue

1. Browse open issues. New contributors should start with `good first issue`.
2. Comment "I'd like to work on this" and wait to be assigned.
3. First-time contributors: one assigned issue at a time.
4. If an assigned issue has no update (comment or PR) for 7 days, a maintainer may ask for a status update and, if there is no reply within 3 more days, unassign it so someone else can pick it up. You are always welcome to claim it again.

## Making changes

1. Create a branch from `main`:
```bash
git checkout -b fix/short-description
```
   Use prefixes: `FIX/`, `FEAT/`, `DOCS/`, `REFACTOR/`.
2. Keep changes small and focused: one issue per pull request.
3. Do not commit build output (`build/` is gitignored) or editor and OS files.

### Coding guidelines

- C++17 only; do not add new dependencies without discussing in an issue first
- Follow the existing naming style in the file you are editing
- Keep each opcode handler small and focused
- Comment the *why* for non-obvious bit manipulation (masks and shifts)
- Avoid unrelated reformatting in your PR

### Testing

There are no automated tests yet. Before opening a PR, run these ROMs from `roms/` and confirm nothing regressed:

- `ibm-logo.ch8`: logo renders correctly
- `pong.ch8`: ball moves, paddle responds to keys
- `tetris.ch8`: loads and runs

In your PR, state which ROMs you tested.

### Commit messages

Short, imperative, descriptive:
```
Add bounds check to LoadROM
Fix out-of-bounds write in Dxyn
```

## Pull request process

1. Push your branch to your fork and open a PR against `main`
2. Link the issue (`Closes #12`)
3. Describe what changed and how you tested it
4. A maintainer will aim to review within 5 days. If you hear nothing after 7 days, feel free to leave a polite ping.
5. Address review comments by pushing to the same branch
6. PRs with no response to review feedback for 14 days may be closed (they can be reopened any time)

## Reporting bugs

Open an issue with: your OS, the exact command you ran, the ROM used, what you expected and what happened.

## Code of conduct

Be respectful and patient. Questions are welcome, and nobody is expected to know everything. Harassment or dismissive behaviour toward other contributors will not be tolerated.

## License

By contributing, you agree that your contributions will be licensed under the project's license (see `LICENSE`).
