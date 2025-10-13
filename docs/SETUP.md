# Detailed Setup Guide

This guide provides step-by-step instructions for setting up the Karlskrona Explore Android application.

## Prerequisites Checklist

- [ ] Android Studio Arctic Fox (2020.3.1) or later
- [ ] Android SDK with API level 21+
- [ ] Java 8 or later
- [ ] Git installed
- [ ] Google account for Firebase and Maps API

## Firebase Setup

### 1. Create Firebase Project
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Create a project"
3. Enter project name: "Karlskrona Explore" (or your preferred name)
4. Enable Google Analytics (optional)
5. Wait for project creation

### 2. Configure Authentication
1. In Firebase Console, go to Authentication > Sign-in method
2. Enable "Email/Password" provider
3. Save changes

### 3. Setup Firestore Database
1. Go to Firestore Database
2. Click "Create database"
3. Choose "Start in test mode" for development
4. Select a location close to your users

### 4. Configure Storage
1. Go to Storage
2. Click "Get started"
3. Use default security rules for development

### 5. Add Android App
1. Click "Add app" and select Android
2. Enter package name: `com.android.mapapp`
3. Download `google-services.json`
4. Place it in `KE/app/` directory

## Google Maps API Setup

### 1. Enable Maps API
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Select your Firebase project
3. Go to APIs & Services > Library
4. Search and enable "Maps SDK for Android"

### 2. Create API Key
1. Go to APIs & Services > Credentials
2. Click "Create Credentials" > "API Key"
3. Copy the API key
4. (Optional) Restrict the key to Android apps and your package name

### 3. Add API Key to Project
1. Create `local.properties` file in `KE/` directory if it doesn't exist
2. Add: `MAPS_API_KEY=your_api_key_here`

## Building the Project

### Using Android Studio
1. Open Android Studio
2. Select "Open an existing project"
3. Navigate to and select the `KE` folder
4. Wait for Gradle sync
5. Connect an Android device or start an emulator
6. Click the "Run" button

### Using Command Line
```bash
cd KE
./gradlew clean
./gradlew assembleDebug
```

## Troubleshooting

### Common Issues

**Gradle Sync Failed**
- Check internet connection
- Update Android Studio
- Invalidate caches and restart

**Maps Not Loading**
- Verify API key is correct
- Check if Maps SDK is enabled
- Ensure device has internet connection

**Firebase Authentication Issues**
- Verify `google-services.json` is in correct location
- Check Firebase project configuration
- Ensure Authentication is enabled

**Build Errors**
- Clean and rebuild project
- Check Android SDK version
- Update dependencies if needed

### Getting Help
- Check the main README for basic setup
- Open an issue on GitHub with error details
- Include device information and Android version