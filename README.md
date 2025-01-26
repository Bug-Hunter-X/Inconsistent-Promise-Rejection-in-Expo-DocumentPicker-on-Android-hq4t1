# Inconsistent Promise Rejection in Expo DocumentPicker on Android

This repository demonstrates a bug in the Expo DocumentPicker API on Android.  The issue involves inconsistent promise rejections from `DocumentPicker.getDocumentAsync()`, even when file selection appears successful and necessary permissions are granted.  The error messages are unreliable, making debugging difficult.

## Bug Report

The core problem is that `DocumentPicker.getDocumentAsync()` sometimes rejects its promise, even when a file has been selected by the user.  This leads to unexpected behavior and a poor user experience. This appears to be related to how Expo handles file URIs on Android, and is particularly apparent on older devices or devices with various Android versions.

## Reproduction

1. Clone this repository.
2. Run the project using Expo Go or a similar method (make sure you have the necessary Android permissions in your `app.json`).
3. Attempt to select a file using the DocumentPicker. Note the inconsistent behavior and potential errors.

## Solution

A workaround has been implemented to consistently handle these cases.  This involves more robust error checking and potential fallback mechanisms to handle the various error scenarios.  The updated file is provided to demonstrate a potential solution to improve reliability.