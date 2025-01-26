# Expo Linking.getInitialURL() Returns Null Inconsistently

This repository demonstrates a bug in the Expo `Linking` API where `getInitialURL()` returns `null` inconsistently, even when a deep link is opened.

## Bug Description
The `Linking.getInitialURL()` method is supposed to return the initial URL that launched the app. However, in certain scenarios (especially on Android), it might return `null` even if the app was launched from a deep link. This makes handling deep links unreliable as the app cannot determine if it was launched with a specific URL.

## Reproduction
1. Clone this repository.
2. Run the app on both Android and iOS emulators/devices.
3. Try launching the app via a deep link (e.g., `myapp://somepath`).
4. Observe that `getInitialURL()` might return `null` in some cases, especially on Android.

## Solution
The solution involves a more robust approach to handling the `null` case, possibly employing a combination of `getInitialURL()` and event listeners to ensure the deep link is captured correctly.   The solution provided handles potential null values and provides more reliable deep link detection.