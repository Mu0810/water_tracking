# Project Plan

Build a complete Android Water Intake Tracker app using Kotlin and Jetpack Compose with Material 3.

Requirements:

UI Design:
- Use a modern Material 3 design.
- Primary color theme: Blue.
- Clean, minimal, premium look.
- Support Light and Dark Mode.

Main Screen:
- Display a large animated CircularProgressIndicator.
- Daily water goal = 2500ml.
- Show current progress percentage visually.
- Display text inside the circle:
  "1250 / 2500 ml"
- Animate progress changes smoothly.

Quick Add Section:
- Add two Material 3 buttons:
  - Glass (+250ml)
  - Bottle (+500ml)
- Add an "Add Custom" TextButton.
- Clicking Add Custom opens a Material 3 AlertDialog.
- Dialog contains:
  - Numeric TextField
  - Cancel button
  - Add button
- Validate input before adding.

Water Logs:
- Show a list of today's entries.
- Example:
  - 10:00 AM - 250ml
  - 12:30 PM - 500ml
- Use LazyColumn.
- New entries appear at the top.
- Allow swipe-to-delete using SwipeToDismissBox.
- Update progress immediately after deletion.

Data Storage:
- Use Room Database.
- Create WaterLog entity:
  - id
  - amountMl
  - timestamp
- Use Repository pattern.
- Persist data locally.

Architecture:
- MVVM Architecture.
- ViewModel with StateFlow.
- Repository layer.
- Room Database.
- Dependency Injection using Hilt.

Features:
- Automatically calculate daily total.
- Reset progress for a new day.
- Show percentage completed.
- Display encouraging messages:
  - Under 25% → "Let's start hydrating!"
  - 25%-75% → "Great progress!"
  - Above 75% → "Almost there!"
  - 100% → "Goal achieved!"

Animations:
- Animated progress indicator.
- Animated visibility for logs.
- Smooth button interactions.

Code Generation:
- Generate complete production-ready code.
- Include:
  - Room Entity
  - DAO
  - Database
  - Repository
  - ViewModel
  - UI Screens
  - Navigation setup
  - Hilt setup
  - Gradle dependencies
- Follow Android Studio latest stable versions.
- Ensure code compiles without errors.

## Project Brief

# Project Brief: Water Tracker MVP

A modern, high
-performance Android application designed to help users reach their daily hydration goals through a premium Material 3 interface and seamless tracking.

## Features

- **Hydration Dashboard**: A central hub featuring a smooth, animated circular progress indicator that visualizes real-time
 progress toward a 2500ml daily goal with dynamic status messages.
- **Flexible Water Logging**: Quick-add buttons
 for common volumes (250ml, 500ml) and a custom input dialog with validation for precise intake
 tracking.
- **Log Management**: A chronological history of the day's intake using `LazyColumn` with `Swipe
ToDismissBox` support for easy deletion and immediate progress updates.
- **Persistent Progress**: Local data storage using Room Database
 to ensure all water logs are saved and progress is automatically calculated across app restarts.

## High-Level Technical Stack
- **
Language**: Kotlin
- **UI Framework**: Jetpack Compose with Material 3 (Light and Dark Mode support)
- **
Architecture**: MVVM (Model-View-ViewModel) with Repository pattern
- **Navigation**: Jetpack Navigation 3 (State-
driven)
- **Adaptive Strategy**: Compose Material Adaptive library for responsive layouts
- **Persistence**: Room Database
- **Dependency Injection**: Hilt
- **Concurrency**: Kotlin Coroutines & Flow for reactive UI updates

## Implementation Steps

### Task_1_Core_Setup_Data: Configure Hilt dependencies and implement the Room data layer (Entity, DAO, Database) and Repository.
- **Status:** IN_PROGRESS
- **Updates:** Updating libs.versions.toml and build.gradle files with Hilt and Room configuration.
- **Acceptance Criteria:**
  - Hilt dependencies added to gradle files
  - Room Entity (WaterLog), DAO, and Database implemented
  - Repository pattern implemented for data access
  - Project builds successfully

### Task_2_Logic_ViewModel: Set up Hilt DI modules and implement the WaterViewModel to handle daily water intake logic, progress calculation, and state management.
- **Status:** PENDING
- **Acceptance Criteria:**
  - Hilt modules for DB and Repository injection are ready
  - ViewModel manages StateFlow for UI
  - Daily reset logic and progress calculation implemented
  - Encouraging messages logic added based on progress

### Task_3_UI_Compose: Build the Jetpack Compose UI including the animated circular progress indicator, quick add buttons, custom input dialog, and the logs list with swipe-to-delete.
- **Status:** PENDING
- **Acceptance Criteria:**
  - Main screen with Animated CircularProgressIndicator implemented
  - Quick add buttons and Custom Add Dialog functional
  - LazyColumn logs with SwipeToDismissBox implemented
  - UI follows Material 3 design and responsiveness

### Task_4_Theme_Finalize: Apply the Blue Material 3 theme (Light/Dark mode), implement the app icon, add animations, and perform a final run and verify.
- **Status:** PENDING
- **Acceptance Criteria:**
  - Vibrant Blue Material 3 theme (Light/Dark) applied
  - Adaptive app icon matching the water tracking theme created
  - Edge-to-edge display implemented
  - Application stability verified (no crashes)
  - Confirm alignment with user requirements and report critical UI issues

