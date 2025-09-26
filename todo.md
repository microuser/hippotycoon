# MARS: Hippo Tycoon - Day/Night Cycle & Story Progression Todo List

This document outlines the development tasks for implementing a day/night cycle and a 4-day story progression feature in the MARS Hippo Simulation game. It is based on the `mars_hippo_game_design.md` document and an analysis of the existing `mars_hippo_game.html` codebase.

## Phase 1: Core Day/Night and Sleep Mechanics

**Objective:** Implement the foundational systems for time progression, an energy stat for MARS, and visual day/night transitions.

**User Story 1.1: Tiredness Mechanic**
*As a player, I want MARS to get tired over time so that natural sleep cycles create story progression opportunities.*

- [x] **Task 1.1.1: Add `energy` Stat**
    - Implemented in `mars_hippo_game.html`: `marsStats.energy = 100` added to stats.

- [x] **Task 1.1.2: Implement Energy Drain**
    - Implemented in `updateStats()` in `mars_hippo_game.html` with `timeMultiplier` scaling.
    - `marsStats.energy = Math.max(0, marsStats.energy - (drainRate * 0.5));`

- [x] **Task 1.1.3: Implement Game Clock**
    - Implemented `gameTime` (0–24 hours) and `DAY_LENGTH_SECONDS_1X` in `mars_hippo_game.html`.
    - `gameTime` advances in `updateStats()` based on `deltaTime` and `timeMultiplier`.

- [x] **Task 1.1.4: Implement Day/Night Visuals**
    - Added `ambientLight` and `sunLight` globals and `updateEnvironment()` in `mars_hippo_game.html`.
    - Smooth sunrise/sunset interpolation and sun position arc; called each frame in `gameLoop()`.

- [x] **Task 1.1.5: Implement Sleep**
    - Added `sleep` to `ACTIONS`, `evaluateNeeds()` prioritizes sleep at low energy.
    - `completeAction('sleep')` restores energy to 100 and advances `gameTime` to 7:00.

## Phase 2: Story and Dream Sequence Engine

**Objective:** Build a system to manage and display the four dream sequences that drive the story forward.

**User Story 1.2: Dream Sequence Framework**
*As a player, I want to experience MARS's dreams as story sequences so that I understand his character development and life journey.*

- [x] **Task 2.1.1: Create Dream Sequence Data Structure**
    - Implemented `DREAM_SEQUENCES` constant in `mars_hippo_game.html` with age triggers and dialogues.
    - Each dream should have an `ageTrigger` (in days) and an array of `dialogue` bubbles.

- [x] **Task 2.1.2: Create a Story Manager**
    - Implemented `storyManager { currentDay, completedDreams }` and persisted via `saveGame()`/`loadGame()`.

- [x] **Task 2.1.3: Trigger Dream Sequences**
    - Dream eligibility checked during `completeAction('sleep')` via `getNextEligibleDreamIndex()`; runs `startDreamSequence()` before advancing day.

- [x] **Task 2.1.4: Implement Dream Sequence Display**
    - Implemented `startDreamSequence(index, onComplete)` using existing `#story` overlay with timed bubbles; pauses game via `inDream` flag and marks completion.

## Phase 3: UI and Player Interaction

**Objective:** Provide the player with visual feedback on the new systems and a way to interact with them.

- [x] **Task 3.1.1: Add Energy Bar to UI**
    - Added Energy bar element and `updateUI()` wiring in `mars_hippo_game.html`.

- [x] **Task 3.1.2: Add a Clock/Day Display**
    - Added `Day/Time` display and logic to format from `gameTime` and `storyManager.currentDay` in `updateUI()`.

- [x] **Task 3.1.3: Add a Sleep Button**
    - Implemented `#sleepBtn` in controls; wired to `onSleepClick()` which initiates sleep at night or when exhausted.
    - Button enable/disable reflects night/energy and `inDream` state via `updateUI()`.

### Additional Feature: Story Log Popup

- [x] **Task 3.2.1: Story Log UI & Persistence**
    - Added `#storyLogModal` with toggle button and close control.
    - Implemented `storyLog` array, `addToStoryLog()`, and `renderStoryLog()`; persisted via save/load.
    - Dream lines and completion events are recorded during `startDreamSequence()`.

## Phase 4: Integration and Refinement

**Objective:** Ensure all new features work together seamlessly and polish the user experience.

- [x] **Task 4.1.1: Game Completion State**
    - After the 4th dream sequence is completed, the game should enter a "complete" state.
    - Display a congratulatory message to the player, celebrating MARS's journey.
    - The game can continue in a sandbox mode after this.

- [ ] **Task 4.1.2: Balance and Tuning**
    - Playtest and adjust the energy drain rate, the length of the day/night cycle, and the age triggers for dreams to ensure the game progression feels natural and engaging.

- [ ] **Task 4.1.3: Code Cleanup**
    - Refactor new code into logical functions and objects.
    - Ensure all new variables are properly scoped and named.
    - Add comments to explain the new, complex parts of the system (e.g., the day/night light interpolation).
