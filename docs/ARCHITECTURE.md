# Architecture Overview

This document describes the architecture and design patterns used in the Karlskrona Explore Android application.

## Architecture Pattern

The app follows the **MVVM (Model-View-ViewModel)** architecture pattern with the following components:

### Model Layer
- **Data Classes**: `PlaceData.kt`, `UserData.kt`
- **Firebase Integration**: `MainViewmodel.kt`
- **Utilities**: `Constants.kt`, `SharedPref.kt`

### View Layer
- **Activities**: `MainActivity.kt`, `MapsActivity.kt`
- **Fragments**: All UI fragments in the `ui` package
- **Adapters**: `PlaceAdapter.kt` for RecyclerView

### ViewModel Layer
- **MainViewmodel.kt**: Handles business logic and Firebase operations

## Package Structure

```
com.android.mapapp/
├── adapter/           # RecyclerView adapters
├── data/             # Data models and classes
├── firebase/         # Firebase integration and ViewModels
├── others/           # Utilities, constants, and helpers
└── ui/               # User interface components
    ├── login/        # Authentication screens
    ├── map/          # Map-related activities
    └── place/        # Place management screens
```

## Key Components

### Authentication Flow
1. **SplashScreenFragment**: App entry point
2. **LoginFragment**: User login
3. **SignupFragment**: User registration
4. **HomeFragment**: Main dashboard after login

### Place Management
1. **CategoryFragment**: Browse place categories
2. **ViewPlaceFragment**: Display place details
3. **AddPlaceFragment**: Add new places
4. **AddTransportationFragment**: Specialized for transportation

### Map Integration
- **MapsActivity**: Google Maps integration
- Displays place markers and user location

### Data Flow
1. User interacts with UI (Fragment/Activity)
2. UI calls ViewModel methods
3. ViewModel interacts with Firebase
4. Data flows back through LiveData/observers
5. UI updates automatically

## Firebase Services

### Authentication
- Email/password authentication
- User session management

### Firestore Database
- Places collection with categories
- User profiles and preferences
- Real-time data synchronization

### Storage
- Image uploads for places
- User profile pictures

## Navigation
- Uses Android Navigation Component
- Single Activity architecture with multiple fragments
- Navigation graph defined in `nav_graph.xml`

## Design Patterns Used

1. **Observer Pattern**: LiveData for reactive UI updates
2. **Repository Pattern**: Centralized data access through ViewModel
3. **Adapter Pattern**: RecyclerView adapters for list displays
4. **Singleton Pattern**: SharedPreferences wrapper

## Dependencies

### Core Android
- AndroidX libraries
- Material Design Components
- Navigation Component
- ViewBinding

### Firebase
- Authentication
- Firestore
- Storage
- Analytics
- Crashlytics

### Third-party
- **Glide**: Image loading and caching
- **Google Maps**: Map functionality
- **Retrofit**: HTTP client (if needed for external APIs)

## Future Improvements

1. **Repository Layer**: Add proper repository pattern
2. **Dependency Injection**: Implement Hilt or Dagger
3. **Testing**: Add unit and integration tests
4. **Offline Support**: Cache data for offline usage
5. **Performance**: Implement pagination for large datasets