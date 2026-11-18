# My Plants 🌱

A simple iOS app that helps you keep your plants alive. Add your plants with their care details, check them off as you water them each day, follow your progress, and get a reminder notification when each plant is due for watering.

## Features

- **Add plant reminders**: set the plant name, room, light, watering frequency and water amount.
- **Edit & delete**: tap a plant to edit it or delete it from the edit screen, or swipe a row left to delete it.
- **Daily checklist**: tap the circle next to a plant to mark it as watered. Watered plants show a green checkmark and a dimmed name.
- **Progress bar**: the bar and message at the top fill up as you water your plants ("3 of your plants feel loved today✨").
- **All Done screen**: shows a celebration screen when every plant has been watered.
- **Daily reset**: checkmarks clear automatically on a new day.
- **Watering notifications**: each plant gets its own repeating local notification based on its watering frequency ("Hey! let's water your Monstera 🌱"). Notifications update when a plant is edited, are cancelled when it is deleted, and also show while the app is open.
- **Persistent storage**: plants are saved on the device and kept after the app is closed.
- **Empty states**: a welcome screen for new users and a "No reminders set yet.." screen after all plants are deleted.

## Built With

- **Swift** & **SwiftUI**
- **SwiftData**: local storage for plants
- **UserNotifications**: local watering reminders
- **MVVM** architecture with the `@Observable` macro
- **Sketch**: UI design

## Requirements

- Xcode 27 or later
- iOS 27.0 or later

## How to Run

1. Download or clone this repository.
2. Open `My Plants.xcodeproj` in Xcode.
3. Select an iPhone simulator or a connected device.
4. Press **Run** (⌘R).
5. Add your first plant and allow notifications when prompted.

> **Testing notifications:** the **🔔 Test** button in the navigation bar sends a test notification after 10 seconds. It is a temporary debug button.

## Project Structure

| File | Description |
|---|---|
| `MyApp.swift` | App entry point. Opens `MyPlantsView` and sets up the SwiftData container for `Plant`. |
| `Models/Plant.swift` | The `Plant` SwiftData model: id, name, room, light, watering days, water amount, watered state and creation date. |
| `ViewModels/MyPlantsViewModel.swift` | Logic for the main screen: fetches plants, toggles watered state, deletes plants, resets checkmarks each new day, calculates progress, and keeps notifications in sync with the plants. |
| `ViewModels/SetReminderViewModel.swift` | Logic for the add/edit screen: holds the form fields and picker options, and saves or deletes a plant. |
| `ViewModels/NotificationManager.swift` | Handles local notifications: requests permission, schedules a repeating notification per plant, cancels it, and shows notifications while the app is open. |
| `Views/MyPlantsView.swift` | The main screen and its states: welcome, plant list with progress bar, All Done, and No Reminders. |
| `Views/SetReminderView.swift` | The add/edit sheet: plant name field, room, light, watering days and water pickers, and a delete button when editing. |

## Author

**Hend**
