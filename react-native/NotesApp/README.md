# React Native Notes App - Setup Guide

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Expo CLI
- iOS Simulator (Mac only) or Android Emulator
- Appwrite account

## Installation Steps

### 1. Install Dependencies

```bash
cd react-native/NotesApp
npm install
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

### 3. Start the Development Server

```bash
npm start
```

### 4. Run on Device/Emulator

**Option 1: Physical Device**
- Install Expo Go app from App Store or Play Store
- Scan the QR code displayed in the terminal

**Option 2: iOS Simulator** (Mac only)
- Press `i` in the terminal

**Option 3: Android Emulator**
- Make sure an Android emulator is running
- Press `a` in the terminal

## Project Structure

```
NotesApp/
├── App.js                  # Main app component with navigation
├── screens/
│   ├── HomeScreen.js      # Welcome screen
│   └── NotesScreen.js     # Notes list and management
├── components/
│   ├── NoteItem.js        # Individual note display
│   ├── AddNoteModal.js    # Modal for creating notes
│   └── EditNoteModal.js   # Modal for editing notes
└── services/
    ├── appwrite-config.js  # Appwrite client configuration
    ├── database-service.js # Database operations
    └── note-service.js     # Note-specific operations
```

## Available Scripts

### `npm start`
Starts the Expo development server

### `npm run android`
Opens the app in an Android emulator

### `npm run ios`
Opens the app in an iOS simulator

### `npm run web`
Opens the app in a web browser

## Troubleshooting

### Issue: "Metro bundler is not starting"
**Solution**: Clear the cache
```bash
npx expo start -c
```

### Issue: "Module not found"
**Solution**: Reinstall dependencies
```bash
rm -rf node_modules
npm install
```

### Issue: "Environment variables not loading"
**Solution**: Restart the development server after changing .env file

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
✅ Responsive UI for different screen sizes

## Next Steps

1. Implement user authentication
2. Add note categories or tags
3. Implement search functionality
4. Add rich text editing
5. Enable note sharing

## Resources

- [React Native Documentation](https://reactnative.dev/)
- [Expo Documentation](https://docs.expo.dev/)
- [React Navigation](https://reactnavigation.org/)
- [Appwrite Documentation](https://appwrite.io/docs)
