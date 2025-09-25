# MARS: Hippo Tycoon - Day/Night Cycle & Story Progression Todo List

This document outlines the development tasks for implementing a day/night cycle and a 4-day story progression feature in the MARS Hippo Simulation game. It is based on the `mars_hippo_game_design.md` document and an analysis of the existing `mars_hippo_game.html` codebase.

## Phase 1: Core Day/Night and Sleep Mechanics

**Objective:** Implement the foundational systems for time progression, an energy stat for MARS, and visual day/night transitions.

**User Story 1.1: Tiredness Mechanic**
*As a player, I want MARS to get tired over time so that natural sleep cycles create story progression opportunities.*

- [ ] **Task 1.1.1: Add `energy` Stat**
    - In the `marsStats` object (around line 337), add a new stat: `energy: 100`.

- [ ] **Task 1.1.2: Implement Energy Drain**
    - In the `updateStats` function (around line 1360), add logic to gradually decrease `marsStats.energy` over time. The drain rate should be affected by `timeMultiplier`.
    - `marsStats.energy = Math.max(0, marsStats.energy - (drainRate * 0.5));`

- [ ] **Task 1.1.3: Implement Game Clock**
    - Create a new global variable `gameTime` to track the time of day (0-24). 
    - In the `updateStats` function, increment `gameTime` based on `deltaTime` and `timeMultiplier`. A full 24-hour cycle should take a reasonable amount of real-time (e.g., 10-15 minutes on 1x speed).

- [ ] **Task 1.1.4: Implement Day/Night Visuals**
    - In the `gameLoop` (around line 1498), create a new function `updateEnvironment(gameTime)`.
    - This function should adjust the properties of `scene.background`, `ambientLight`, and `directionalLight` based on the `gameTime` to simulate sunrise, day, sunset, and night.
    - *Day (6-18)*: Bright light, blue sky.
    - *Night (19-5)*: Dark light (not completely black), dark blue/black sky, maybe add stars (optional).
    - *Transitions*: Smoothly interpolate the light color/intensity and background color during sunrise and sunset.

- [ ] **Task 1.1.5: Implement Sleep**
    - Create a new `sleep` action in the `ACTIONS` constant (around line 325).
    - When MARS's energy reaches 0, the `marsAI` should trigger a `sleep` action.
    - The sleep action should restore energy and advance the game time quickly to the next morning (e.g., 7 AM).

## Phase 2: Story and Dream Sequence Engine

**Objective:** Build a system to manage and display the four dream sequences that drive the story forward.

**User Story 1.2: Dream Sequence Framework**
*As a player, I want to experience MARS's dreams as story sequences so that I understand his character development and life journey.*

- [ ] **Task 2.1.1: Create Dream Sequence Data Structure**
    - Create a new constant, `DREAM_SEQUENCES`, to hold the story content for each of the four dreams as described in `mars_hippo_game_design.md`.
    - Each dream should have an `ageTrigger` (in days) and an array of `dialogue` bubbles.

- [ ] **Task 2.1.2: Create a Story Manager**
    - Create a new global object, `storyManager`, to track story progression. It should include `currentDay: 1` and `completedDreams: []`.
    - This state should be saved and loaded in the `saveGame()` and `loadGame()` functions.

- [ ] **Task 2.1.3: Trigger Dream Sequences**
    - When MARS goes to sleep, check if the current `marsStats.age` meets the `ageTrigger` for the next dream and if it hasn't been completed yet.
    - If conditions are met, initiate the dream sequence *before* advancing to the next day.

- [ ] **Task 2.1.4: Implement Dream Sequence Display**
    - Create a new function `showDreamSequence(dream)`.
    - This function should display a modal overlay (similar to the existing `#story` div) and show the dialogue bubbles one by one.
    - After the dream sequence is over, mark it as complete in the `storyManager` and then proceed to the next day.

## Phase 3: UI and Player Interaction

**Objective:** Provide the player with visual feedback on the new systems and a way to interact with them.

- [ ] **Task 3.1.1: Add Energy Bar to UI**
    - In the HTML (around line 235), add a new stat bar for Energy.
    - In `updateUI()` (around line 1415), update the energy bar's width based on `marsStats.energy`.

- [ ] **Task 3.1.2: Add a Clock/Day Display**
    - In the UI, add an element to display the current day and time (e.g., "Day 1, 14:00").
    - Update this display in the `updateUI()` function.

- [ ] **Task 3.1.3: Add a Sleep Button**
    - Add a "Sleep" button to the controls panel in the HTML.
    - When it's evening/night in the game and MARS's energy is low, enable the button.
    - Clicking the button will command MARS to find a spot to sleep and trigger the sleep cycle.

## Phase 4: Integration and Refinement

**Objective:** Ensure all new features work together seamlessly and polish the user experience.

- [ ] **Task 4.1.1: Game Completion State**
    - After the 4th dream sequence is completed, the game should enter a "complete" state.
    - Display a congratulatory message to the player, celebrating MARS's journey.
    - The game can continue in a sandbox mode after this.

- [ ] **Task 4.1.2: Balance and Tuning**
    - Playtest and adjust the energy drain rate, the length of the day/night cycle, and the age triggers for dreams to ensure the game progression feels natural and engaging.

- [ ] **Task 4.1.3: Code Cleanup**
    - Refactor new code into logical functions and objects.
    - Ensure all new variables are properly scoped and named.
    - Add comments to explain the new, complex parts of the system (e.g., the day/night light interpolation).
