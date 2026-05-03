# Babble — Ruleset

**Code:** BAB  
**Version:** 0.0.0

## Overview

Babble is a trivia-meets-Scrabble game. Answer trivia questions, spell the answer from a letter rack, and watch your word auto-placed on a 15×15 board for points. Multiplier squares, pass mechanics, and a seed-based challenge mode make every game count.

---

## Board

- 15×15 grid with standard Scrabble-style multiplier layout
- Multiplier squares: **2L** (double letter), **3L** (triple letter), **2W** (double word), **3W** (triple word), **★** (center — double word)
- Each multiplier applies only once; re-used cells score at face value

## Questions

- 40 trivia questions across 7 categories: Science & Nature, Geography, History, Literature & Arts, Vocabulary, Animals, General
- Questions are shuffled each game using a seeded RNG
- The answer is always a single English word (all caps on the board)

## Tile Rack

- Each question generates a rack of 15–20 tiles
- Rack contains all letters of the answer plus random fillers
- Tap/click tiles to spell your answer; tap a placed tile to return it to the rack

## Placement

- First word is placed horizontally, centred on the star square
- Subsequent words must intersect at least one existing letter
- The game finds the highest-scoring valid placement automatically
- If no valid placement exists, 0 points are awarded for that turn

## Scoring

- Each letter scores its Scrabble point value
- New tiles landing on multiplier squares apply that square's bonus
- Word multipliers (2W, 3W, ★) stack with letter multipliers in the same placement
- Multiplier squares already used by a previous word score at face value only

## Pass Mechanic

- **First pass:** question moves to the back of the queue
- **Second pass on the same question:** question is skipped, 0 points awarded

## End of Game

- Game ends when all questions have been answered or skipped
- Final score, best score, and board are shown on the end screen
- Share your result as plain text

## Challenge / Seed Mode

- Enter a hex seed to play a specific question order — useful for competing with a friend on identical conditions
- Seeds are shareable; the same seed always produces the same question sequence and rack shuffle

## Stats

- Stored locally (localStorage key: `BAB_stats`)
- Tracks: games played, total score, personal best
- Stats persist between sessions; use the Holly console command `send;plyrwipe` to reset

---

*Babble is a Tacticon Studios original.*
