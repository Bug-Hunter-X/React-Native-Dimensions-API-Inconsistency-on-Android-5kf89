# React Native Dimensions API Inconsistency on Android

This repository demonstrates a bug related to inconsistent screen dimensions returned by the `Dimensions` API in React Native, specifically on Android devices. The problem is that `Dimensions.get('window')` or `Dimensions.get('screen')` can return incorrect values, especially during app initialization or after screen rotation. This results in layout problems, where UI elements are rendered in the wrong positions or with incorrect sizes.

## Steps to Reproduce

1. Clone the repository.
2. Run the app on an Android emulator or device.
3. Observe the initial layout and then rotate the screen.  The layout might become distorted or components may be misaligned.

## Solution

The provided solution demonstrates a workaround to mitigate this issue by listening for layout changes and updating the dimensions accordingly. Using the `onLayout` event allows you to accurately measure component dimensions after the layout has fully rendered, ensuring the dimensions are correct and consistent.