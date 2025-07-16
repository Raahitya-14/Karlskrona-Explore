# Karlskrona Explore

Karlskrona Explore is an Android application created as a student project at BTH. It helps visitors and residents discover different places in Karlskrona. The app organizes locations in several categories such as **Tourist attractions**, **Accommodation**, **Restaurant**, **Transportation**, **Grocery** and **Shopping**. Users can add their own places with photos and ratings or browse existing entries on a map.

## Build and setup

1. Clone this repository
   ```bash
   git clone <repo-url>
   cd Karlskrona-Explore/KE
   ```
2. Open the project in Android Studio **or** build from the command line:
   ```bash
   ./gradlew assembleDebug
   ```

Prerequisites:
- Android Studio (or the Android SDK command line tools)
- A configured Firebase project. Replace the bundled `google-services.json` with your own configuration if needed.

## Usage

After installing the debug APK on an Android device you can:

1. Sign up or log in.
2. Choose a category to view places in Karlskrona.
3. Press **Add Place** to submit a new location with name, description, coordinates, category and photo.
4. Tap an item in the list to view it on the map.

Example screens:

![Splash](KE/app/src/main/res/drawable/splash.png)
![Categories](KE/app/src/main/res/drawable/touristattraction.png)

## License

This project is provided for educational purposes. Feel free to open issues or pull requests if you wish to contribute.
