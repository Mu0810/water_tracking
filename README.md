# Water Tracking

An Android water-intake tracker, planned in Kotlin with Jetpack Compose and Material 3.

> **Status: scaffold only. The app is not implemented yet.**
>
> This repository currently contains the generated Android Studio project skeleton and nothing more.
> `MainActivity` still renders the template's `Greeting` composable ("Hello Android!"), and the only
> tests present are the two stock examples. None of the tracking features described below exist yet.

---

## What is actually here

| Path | Contents |
| --- | --- |
| `app/src/main/java/.../MainActivity.kt` | unmodified template activity with a `Greeting` composable |
| `app/src/main/java/.../ui/theme/` | generated `Color.kt`, `Theme.kt`, `Type.kt` (light/dark scaffolding) |
| `app/src/test/` | `ExampleUnitTest.kt` — the default stub |
| `app/src/androidTest/` | `ExampleInstrumentedTest.kt` — the default stub |
| `.agent/plan.md` | the intended feature set |

Around 185 lines of Kotlin in total, essentially all of it generated.

## Configuration

Real, and worth noting since it is the one part that has been set up deliberately:

- `compileSdk` 36, `targetSdk` 36, `minSdk` 24
- Jetpack Compose enabled (`buildFeatures.compose = true`)
- Java 11 source/target compatibility
- Plugins wired via a version catalog: Android application, Kotlin Compose, **KSP**, and
  **kotlinx.serialization** — KSP and serialization suggest Room and persisted state were the
  intended direction

## Planned features

From `.agent/plan.md`, none of which is built yet:

- Material 3 UI with a blue primary colour, supporting light and dark mode
- A main screen with a large animated `CircularProgressIndicator` against a 2,500 ml daily goal,
  showing `current / goal ml` inside the ring and animating progress changes
- Quick-add buttons for a glass (+250 ml) and a bottle (+500 ml), plus a custom amount
- History and daily reset

## Building

```bash
./gradlew assembleDebug
```

Requires JDK 11+ and the Android SDK (API 36). Opening the project in Android Studio and running it
will currently show the template screen.

## Honest next step

This is a starting point, not a product. Anyone arriving here looking for a working water tracker
should know that up front — hence this README rather than a feature list implying otherwise.

The first meaningful commit would be the main screen: a `ViewModel` holding intake state, a Room
entity for a logged drink, and the progress ring wired to the quick-add buttons.
