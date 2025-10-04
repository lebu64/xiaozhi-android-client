# Flutter Installation and Configuration Guide

This document provides detailed instructions for installing and configuring the AI Assistant application, including environment setup, dependency installation, and platform-specific configuration steps.

## 1. Flutter SDK Installation

### Windows
1. Download [Flutter SDK](https://flutter.dev/docs/get-started/install/windows)
2. Extract to a directory without special characters or spaces (e.g., `C:\flutter`)
3. Add `flutter\bin` to the system PATH variable
4. Open Command Prompt or PowerShell, run `flutter doctor` to verify and resolve potential issues

### macOS
1. Install using Homebrew (recommended):
   ```bash
   brew install --cask flutter
   ```
2. Or download [Flutter SDK](https://flutter.dev/docs/get-started/install/macos) and extract manually
3. Add Flutter to PATH:
   ```bash
   export PATH="$PATH:`pwd`/flutter/bin"
   ```
4. Run `flutter doctor` to check configuration

### Linux
1. Download [Flutter SDK](https://flutter.dev/docs/get-started/install/linux)
2. Extract files:
   ```bash
   tar xf flutter_linux_3.7.0-stable.tar.xz
   ```
3. Add Flutter to PATH:
   ```bash
   export PATH="$PATH:`pwd`/flutter/bin"
   ```
4. Run `flutter doctor` for configuration check

## 2. Install Development Tools

Recommended to use one of the following IDEs for development:

- **Visual Studio Code**
  - Install [Flutter plugin](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter)
  - Install [Dart plugin](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code)

- **Android Studio / IntelliJ IDEA**
  - Install Flutter and Dart plugins (Preferences > Plugins > Search "Flutter")

## 3. Platform-Specific Settings

### Android Development
1. Install [Android Studio](https://developer.android.com/studio)
2. Install Android SDK (via Android Studio's SDK Manager)
3. Set up Android device for development:
   - Enable USB debugging (Developer Options)
   - Or use Android emulator

### iOS Development (macOS only)
1. Install [Xcode](https://apps.apple.com/us/app/xcode/id497799835)
2. Configure iOS simulator or physical device
3. Install CocoaPods:
   ```bash
   sudo gem install cocoapods
   ```

### Web Development
1. Ensure Chrome browser is installed
2. Enable Flutter web support:
   ```bash
   flutter config --enable-web
   ```

### Windows/macOS/Linux Desktop App Development
1. Enable corresponding platform support:
   ```bash
   # Windows
   flutter config --enable-windows-desktop
   
   # macOS
   flutter config --enable-macos-desktop
   
   # Linux
   flutter config --enable-linux-desktop
   ```

## 4. Project Setup

1. Clone the project repository:
   ```bash
   git clone https://github.com/your-username/ai_assistant.git
   cd ai_assistant
   ```

2. Get dependencies:
   ```bash
   flutter pub get
   ```

3. Configure Firebase or other cloud services as needed (if applicable)

## 5. Configure AI Services

### Xiaozhi Service Configuration
1. Navigate to "Settings" > "Xiaozhi Service" in the app
2. Enter the following information:
   - Name: Specify an identification name for this configuration
   - WebSocket URL: WebSocket connection address for Xiaozhi service
   - MAC Address: Device MAC address (for Bluetooth devices)
   - Token: Authentication token

### Dify Configuration
1. Visit [Dify official website](https://dify.ai/) to create an account and get API key
2. Add new Dify configuration in app settings:
   - Name: Custom configuration name
   - API Key: Key obtained from Dify console
   - API URL: API endpoint for Dify service

### OpenAI Configuration
1. Get API key from [OpenAI Developer Platform](https://platform.openai.com/)
2. Configure in app settings:
   - API Key: OpenAI API key
   - Organization ID (optional): Fill if you have an organization account
   - Model: Select desired GPT model (e.g., gpt-4, gpt-3.5-turbo)
   - System Prompt: Set default system prompt

## 6. Run the Application

```bash
# Run on connected device
flutter run

# Run on specific platform
flutter run -d windows
flutter run -d macos
flutter run -d chrome
flutter run -d <device-id>
```

## 7. Build Release Version

```bash
# Android APK
flutter build apk --release

# Android App Bundle
flutter build appbundle --release

# iOS
flutter build ios --release

# Web
flutter build web --release

# Windows
flutter build windows --release

# macOS
flutter build macos --release

# Linux
flutter build linux --release
```

## 8. Permission Description

The application may require the following permissions:
- **Microphone**: For voice recognition and recording functions
- **Bluetooth**: For connecting IoT devices
- **Camera**: For visual recognition functions
- **Storage**: For saving audio and image files

Please ensure to grant required permissions before using corresponding functions.

## 9. Troubleshooting

### Common Issues

1. **Flutter SDK Not Found**
   - Confirm Flutter is correctly added to system PATH
   - Check `flutter doctor` output for errors

2. **Dependency Fetch Failed**
   - Try using domestic mirror sources:
     ```bash
     export PUB_HOSTED_URL=https://pub.flutter-io.cn
     export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
     ```
   - Clear cache and retry:
     ```bash
     flutter clean
     flutter pub cache repair
     flutter pub get
     ```

3. **Compilation Error**
   - View detailed error information: `flutter run -v`
   - Ensure using supported Flutter SDK version (^3.7.0)

4. **iOS Build Failed**
   - Delete Pods directory and reinstall:
     ```bash
     cd ios
     rm -rf Pods
     pod install
     cd ..
     flutter run
     ```

5. **Android Gradle Sync Failed**
   - Edit `android/gradle.properties` to add proxy settings or use domestic mirror

## 10. Reference Resources

- [Flutter Official Documentation](https://flutter.dev/docs)
- [Dart Official Documentation](https://dart.dev/guides)
- [Flutter Pub Package Management](https://pub.dev/)
- [Flutter Community Chinese Resources](https://flutter.cn/)
