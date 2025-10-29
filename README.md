# Flutter Timer App

A simple yet elegant timer application built with Flutter and BLoC pattern. This app demonstrates the implementation of a countdown timer with basic controls and clean architecture.

## Features

- 60-second countdown timer
- Start, pause, resume, and reset functionality
- Clean UI with gradient background
- Built using BLoC pattern for state management
- Reactive programming with Streams

## Architecture

The app is structured into several key components:

### 1. Ticker
The core timing mechanism that provides a stream of countdown values:
- Located in `lib/ticker.dart`
- Generates periodic events every second
- Counts down from a specified duration

### 2. Timer BLoC
Manages the business logic and state of the timer:
- Located in `lib/timer/bloc/`
- Handles timer events (start, pause, resume, reset)
- Maintains different timer states
- Manages timer subscriptions

#### States:
- `TimerInitial`: Starting state (60 seconds)
- `TimerRunInProgress`: Timer is counting down
- `TimerRunPause`: Timer is paused
- `TimerRunComplete`: Timer has finished

#### Events:
- `TimerStarted`: Begin countdown
- `TimerPaused`: Pause countdown
- `TimerResumed`: Resume countdown
- `TimerReset`: Reset to initial state

### 3. UI Components
Clean and responsive user interface:
- Located in `lib/timer/timer_page.dart`
- Shows current countdown in MM:SS format
- Dynamic action buttons based on timer state
- Smooth gradient background
- Responsive layout

## Project Structure
```
lib/
├── main.dart
├── app.dart
├── ticker.dart
└── timer/
    ├── timer_page.dart
    └── bloc/
        ├── timer_bloc.dart
        ├── timer_event.dart
        └── timer_state.dart
```

## Dependencies

- `flutter_bloc`: State management
- `equatable`: Value equality
- `bloc`: Business logic components

## Getting Started

1. Clone the repository
2. Run `flutter pub get` to install dependencies
3. Run `flutter run` to start the app

## Implementation Details

- Uses sealed classes for type-safe event and state handling
- Implements proper resource management (subscription cancellation)
- Utilizes BLoC pattern for separation of concerns
- Employs efficient UI updates using `BlocBuilder` with `buildWhen`
- Features a clean, material design-based UI

## Contributing

Feel free to submit issues and enhancement requests.
