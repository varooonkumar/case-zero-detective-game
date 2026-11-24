# 🕵️ Case Zero – Detective Mystery Simulator (v2)

A text-based detective mystery game written in **x86 Assembly (MASM)** using the **Irvine32** library. Built as a project for the **EL-2003 Computer Organization & Assembly Language (COAL)** lab at FAST-NUCES Karachi.

---

## 📖 Story

During the annual charity gala at **Blackwood Manor**, the priceless **Blue Diamond** vanishes from a locked study. The study clock stopped at exactly **9:00 PM**.

Four people were in the house that night, and one of them is the thief:

| Suspect | Role |
|---|---|
| Mr. Hale | The butler |
| Maria Costa | The chef |
| Victor Lane | The gardener |
| Clara Blackwood | The niece |

You are the detective. Search for clues, question the suspects, confront them with evidence, and decide who did it.

---

## 🎮 Gameplay

- **Search a location** to find clues (+10 points for each new clue)
- **Question a suspect** to record their statement (+5 points for each new suspect)
- **Confront a suspect with evidence**: guilty suspects crack, innocent ones don't (+10 points for each useful reaction)
- **Solve puzzles**: a numeric safe-code puzzle and a clock riddle (+20 points for a correct answer, -5 for a wrong one)
- **Review evidence & notes** and check the **case status** at any time
- **Make the final accusation**: you need at least **3 clues** first. A wrong accusation closes the case in failure.

### Endings
- 🏆 **Master Detective**: correct accusation with a high score (120 or more)
- 🍀 **Lucky Guess**: correct culprit, but you missed much of the evidence
- ❌ **Case Failed**: wrong accusation (the real culprit is revealed)

After the game ends, a pop-up asks if you want to play again. The culprit is random each time, so the truth changes from game to game.

---

## 🕹️ Controls

| Key | Action |
|---|---|
| `UP` / `DOWN` or `W` / `S` | Move the highlight bar |
| `ENTER` | Select |
| `ESC` | Go back |

---

## ✨ Features

- Arrow-key menus with a highlight bar
- **Two different cases** (the culprit is chosen randomly every game)
- Evidence confrontation system (suspect × clue reaction table)
- Colored status header showing score, clues, statements and proofs
- Typewriter text effect and a unique color for each suspect
- Yes/No pop-up boxes for the final accusation and replay
- Scoring system with rewards and penalties

---

## 🧩 Code Structure

| Procedure | Purpose |
|---|---|
| `main` | Main game loop and menu dispatch |
| `SetupCase` | Picks a random case and points the current-case pointers to its data |
| `ResetGame` | Clears all game state and the score, then starts a new case |
| `ShowIntro`, `NewScreen`, `ShowHeader` | Intro text, screen clearing and the colored status header |
| `DrawMenu`, `ArrowMenu` | Reusable arrow-key menu engine |
| `TypeString` | Typewriter text effect |
| `CountFlags` | Counts how many flags are set in a state array |
| `InspectClue` | Searching locations and logging clues |
| `QuestionSuspect` | Questioning suspects and saving statements |
| `BuildEvidenceMenu`, `Confront` | Builds the evidence menu and handles confrontations |
| `SolvePuzzle` | Runs the puzzles and checks answers |
| `ToLowerStr`, `TrimTrail`, `CompareStrings` | String helpers for checking typed answers |
| `ShowEvidence` | Evidence board, suspect notes and confrontation log |
| `ShowStatus` | Case progress and score |
| `CheckAccusation` | Final accusation, ending and score rank |

---

## 🧠 Assembly Concepts Demonstrated

- **Arrays and flag tables** for game state (`clueFound`, `suspectAsked`, `puzzleDone`)
- **2D table addressing** using `row * NUM_CLUES + column` for suspect × clue reactions
- **Indirect addressing** through pointer tables (`curClueTable`, `curConfrontTable`, etc.) to switch between cases
- **Procedures** with stack save/restore (`push` / `pop`)
- **String instructions** (`STOSB`) and string comparison
- **Conditional jumps and loops** for the game logic
- **Irvine32 library calls**: `ReadKey`, `Gotoxy`, `SetTextColor`, `Randomize`, `RandomRange`, `MsgBoxAsk`, `WriteString`, `WriteDec`, `WaitMsg`

---

## ⚙️ How to Build and Run

### Requirements
- Windows
- Visual Studio with MASM support
- [Irvine32 library](http://www.kipirvine.com/asm/) (set up for Visual Studio)

### Steps
1. Set up an Irvine32 project in Visual Studio.
2. Add `casezero_v2_asm.asm` to the project.
3. Build the solution (x86 / Win32).
4. Run it and start investigating!

---

## 👥 Authors
- **Varoon Kumar**
- **Akshay Kumar Talreja**
- **Kirpa**

FAST-NUCES Karachi – EL-2003 COAL Lab

---

## 📄 License

This project was made for educational purposes.
