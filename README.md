# Karlskrona Explore

Karlskrona Explore is an Android application created as a student project at BTH. It helps visitors and residents discover different places in Karlskrona. The app organizes locations in several categories such as **Tourist attractions**, **Accommodation**, **Restaurant**, **Transportation**, **Grocery** and **Shopping**. Users can add their own places with photos and ratings or browse existing entries on a map.

## Features

- 🗺️ Interactive map with place markers
- 📱 User authentication (sign up/login)
- 📍 Add new places with photos and ratings
- 🏷️ Browse places by category
- 🔍 Search and filter locations
- 📸 Photo upload for places
- ⭐ Rating system

## Project Structure

```
Karlskrona-Explore/
├── KE/                     # Main Android project
│   ├── app/
│   │   ├── src/main/java/com/android/mapapp/
│   │   │   ├── adapter/    # RecyclerView adapters
│   │   │   ├── data/       # Data models
│   │   │   ├── firebase/   # Firebase integration
│   │   │   ├── others/     # Utilities and constants
│   │   │   └── ui/         # UI components (fragments, activities)
│   │   └── src/main/res/   # Resources (layouts, drawables, etc.)
│   └── build.gradle        # App-level build configuration
└── README.md
```

## Prerequisites

- **Android Studio** Arctic Fox (2020.3.1) or later
- **Android SDK** with minimum API level 21
- **Java 8** or later
- **Firebase project** with the following services enabled:
  - Authentication
  - Firestore Database
  - Storage
  - Maps API key

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <repo-url>
cd Karlskrona-Explore
```

### 2. Firebase Configuration
1. Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Authentication, Firestore Database, and Storage
3. Download your `google-services.json` file
4. Replace the existing file at `KE/app/google-services.json`

### 3. Google Maps API
1. Get a Google Maps API key from [Google Cloud Console](https://console.cloud.google.com/)
2. Add the API key to your `local.properties` file:
   ```
   MAPS_API_KEY=your_api_key_here
   ```

### 4. Build the Project

**Option A: Using Android Studio**
1. Open Android Studio
2. Select "Open an existing project"
3. Navigate to and select the `KE` folder
4. Wait for Gradle sync to complete
5. Run the app on a device or emulator

**Option B: Command Line**
```bash
cd KE
./gradlew assembleDebug
```

The APK will be generated at `KE/app/build/outputs/apk/debug/app-debug.apk`

## Usage

1. **Authentication**: Sign up with email/password or log in with existing credentials
2. **Browse Categories**: Select from Tourist attractions, Accommodation, Restaurant, Transportation, Grocery, or Shopping
3. **View Places**: Browse places in each category with details and photos
4. **Add Places**: Tap the "+" button to add new locations with:
   - Name and description
   - GPS coordinates (auto-detected or manual)
   - Category selection
   - Photo upload
   - Rating
5. **Map View**: Tap any place to view its location on the map
6. **Profile**: Manage your account and view your added places

## Technical Details

- **Language**: Kotlin
- **Architecture**: MVVM with ViewBinding
- **Backend**: Firebase (Auth, Firestore, Storage)
- **Maps**: Google Maps Android API
- **Image Loading**: Glide
- **Navigation**: Android Navigation Component
- **Minimum SDK**: 21 (Android 5.0)
- **Target SDK**: 32 (Android 12L)

## Contributing

This project is provided for educational purposes. Feel free to:
- Open issues for bugs or feature requests
- Submit pull requests for improvements
- Fork the project for your own modifications

## License

This project is created for educational purposes as part of a student project at BTH (Blekinge Institute of Technology).
