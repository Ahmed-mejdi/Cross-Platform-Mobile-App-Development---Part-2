# Flutter Notes App - Setup Guide

## Prerequisites

- Flutter SDK (3.0 or higher)
- Dart SDK
- Android Studio / Xcode
- VS Code or Android Studio IDE
- Appwrite account

## Installation Steps

### 1. Install Dependencies

```bash
cd flutter/notes_app
flutter pub get
```

### 2. Configure Environment Variables

Copy the example environment file:

```bash
copy .env.example .env
```

Update `.env` with your Appwrite credentials:

```env
APPWRITE_ENDPOINT=https://cloud.appwrite.io/v1
APPWRITE_PROJECT_ID=your-actual-project-id
APPWRITE_DATABASE_ID=your-actual-database-id
APPWRITE_COLLECTION_ID=your-actual-collection-id
```

### 3. Run the App

```bash
flutter run
```

Select your target device when prompted.

## Project Structure

```
notes_app/
├── lib/
│   ├── main.dart            # App entry point
│   ├── screens/
│   │   ├── home_screen.dart   # Welcome screen
│   │   └── notes_screen.dart  # Notes list and management
│   ├── components/
│   │   ├── note_item.dart         # Individual note widget
│   │   ├── add_note_modal.dart    # Dialog for creating notes
│   │   └── edit_note_modal.dart   # Dialog for editing notes
│   └── services/
│       ├── appwrite_config.dart   # Appwrite client configuration
│       └── note_service.dart      # Note operations
└── pubspec.yaml             # Project configuration
```

## Available Commands

### `flutter run`
Runs the app on a connected device or emulator

### `flutter run -d chrome`
Runs the app in a web browser

### `flutter build apk`
Builds an Android APK

### `flutter build ios`
Builds an iOS app (Mac only)

### `flutter clean`
Cleans the build directory

### `flutter pub get`
Fetches dependencies

### `flutter doctor`
Checks your Flutter installation

## Troubleshooting

### Issue: "Target of URI doesn't exist"
**Solution**: Run `flutter pub get` to install dependencies

### Issue: "Gradle build failed"
**Solution**: 
```bash
cd android
./gradlew clean
cd ..
flutter clean
flutter pub get
```

### Issue: "CocoaPods not installed" (iOS)
**Solution**:
```bash
sudo gem install cocoapods
cd ios
pod install
cd ..
```

### Issue: "Environment variables not loading"
**Solution**: 
- Ensure `.env` file is in the project root
- Verify `pubspec.yaml` includes the asset:
  ```yaml
  flutter:
    assets:
      - .env
  ```
- Run `flutter clean` and rebuild

### Issue: "Appwrite connection error"
**Solution**: 
- Check your Appwrite endpoint URL
- Verify project ID is correct
- Ensure internet connection
- Check Appwrite service status

## Features

✅ Create new notes with title and content
✅ View all notes in a list
✅ Edit existing notes
✅ Delete notes with confirmation
✅ Pull to refresh notes list
✅ Real-time sync with Appwrite backend
✅ Material Design UI
✅ Responsive layout for different screen sizes

## Building for Production

### Android

```bash
flutter build apk --release
```

The APK will be in `build/app/outputs/flutter-apk/app-release.apk`

### iOS (Mac only)

```bash
flutter build ios --release
```

Then open `ios/Runner.xcworkspace` in Xcode to archive and distribute.

## Hot Reload

Flutter supports hot reload for rapid development:
- Press `r` in the terminal to hot reload
- Press `R` to hot restart
- Press `q` to quit

## Running on Specific Devices

### List available devices
```bash
flutter devices
```

### Run on specific device
```bash
flutter run -d <device-id>
```

## Next Steps

1. Implement user authentication
2. Add note categories or tags
3. Implement search functionality
4. Add rich text editing
5. Enable note sharing
6. Add offline support

## Resources

- [Flutter Documentation](https://flutter.dev/docs)
- [Dart Documentation](https://dart.dev/guides)
- [Material Design](https://material.io/design)
- [Appwrite Documentation](https://appwrite.io/docs)
