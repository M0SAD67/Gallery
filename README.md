# 📸 M O S A Gallery

<div align="center">

![M O S A Logo](https://img.shields.io/badge/M_O_S_A-Gallery-00D4AA?style=for-the-badge&logo=flutter&logoColor=white)

**Professional Photo & Video Gallery with Advanced Video Player and Subtitle Support**

[![Flutter](https://img.shields.io/badge/Flutter-3.0+-02569B?style=flat&logo=flutter)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.0+-0175C2?style=flat&logo=dart)](https://dart.dev)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat&logo=android)](https://www.android.com)

[Features](#-features) • [Installation](#️-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Developer](#-developer)

</div>

---

## 🎯 Overview

**M O S A Gallery** is a professional photo and video gallery app built with Flutter, offering a smooth and modern user experience with numerous advanced features.

### ✨ Key Features

#### 📱 **Modern UI/UX**
- 5 different navigation bar designs (Pill Shape, Floating Pills, Holographic, iOS Style, Futuristic)
- Smooth and professional animations
- Dark mode support
- Responsive design that adapts to all screen sizes

#### 🎬 **Advanced Video Player**
- **Full Subtitle Support (SRT/VTT)** with complete customization:
  - Change text and background colors
  - Control font size and position
  - Adjust transparency and width
- **Picture-in-Picture (PIP)** mode for multitasking
- **Gesture Controls**:
  - Vertical swipe for brightness and volume
  - Double tap for forward/rewind
- **Multiple playback speeds** (0.25x - 2.0x)
- Blur effect for privacy
- Auto-save playback position
- Auto-rotate to landscape
- Visual indicators for brightness and volume

#### 🔒 **Security & Privacy**
- **App Lock** with custom passcode
- **Biometric Authentication** (Fingerprint / Face ID)
- **Hide Files** from main gallery
- Password-protected folder for sensitive content

#### 🎨 **Media Management**
- Display photos and videos by date
- **Advanced Search** functionality
- **Multi-selection mode** for batch operations:
  - Share
  - Delete
  - Hide
- **Albums and Collections**
- **Recently Deleted** folder
- Filter by type (photos/videos)

#### ⚡ **Performance**
- Fast thumbnail loading
- Shimmer effect while loading
- Lazy loading for long lists
- Smart image caching
- Optimized memory usage

#### 🌐 **Languages**
- Arabic support
- English support
- Extensible interface for adding new languages

---

## 🛠️ Tech Stack

### Frontend
- **Flutter 3.0+** - Main framework
- **Dart 3.0+** - Programming language

### Core Libraries

#### Media Management
```yaml
photo_manager: ^3.5.3          # Photo & video management
video_player: ^2.9.2           # Video playback
subtitle: ^1.0.2               # Subtitle file processing
open_file: ^3.5.8              # File operations
```

#### Security
```yaml
local_auth: ^2.3.0             # Biometric authentication
flutter_secure_storage: ^9.2.2 # Secure storage
shared_preferences: ^2.3.3     # Settings storage
```

#### User Interface
```yaml
flutter_colorpicker: ^1.1.0    # Color picker
device_info_plus: ^10.1.2      # Device information
```

#### Sharing & Permissions
```yaml
share_plus: ^10.1.2            # File sharing
permission_handler: ^11.3.1    # Permission management
```

#### Additional Tools
```yaml
intl: ^0.19.0                  # Internationalization
path: ^1.9.0                   # Path manipulation
file_picker: ^8.1.4            # File selection
```

---

## 📋 Requirements

### System
- **Android**: 7.0 (API 24) or higher
  - For auto-rotate and advanced animations: Android 10+ (API 29)
  - For file hiding: Android 11+ (API 30) recommended
- **iOS**: 12.0 or higher (not fully tested)

### Development Tools
- Flutter SDK 3.0 or higher
- Dart SDK 3.0 or higher
- Android Studio / VS Code
- Xcode (for iOS development)

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/M0SAD67/mosa-gallery.git
cd mosa-gallery
```

### 2️⃣ Install Dependencies

```bash
flutter pub get
```

### 3️⃣ Configure Permissions

#### Android
Add permissions in `android/app/src/main/AndroidManifest.xml`:

```xml
<!-- Basic permissions -->
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />

<!-- Android 11+ -->
<uses-permission android:name="android.permission.MANAGE_EXTERNAL_STORAGE" />

<!-- Android 13+ -->
<uses-permission android:name="android.permission.READ_MEDIA_IMAGES" />
<uses-permission android:name="android.permission.READ_MEDIA_VIDEO" />

<!-- Biometric -->
<uses-permission android:name="android.permission.USE_BIOMETRIC" />
<uses-permission android:name="android.permission.USE_FINGERPRINT" />

<!-- PIP Mode -->
<activity android:supportsPictureInPicture="true" />
```

#### iOS
Add to `ios/Runner/Info.plist`:

```xml
<key>NSPhotoLibraryUsageDescription</key>
<string>We need access to your photos to display them</string>
<key>NSPhotoLibraryAddUsageDescription</key>
<string>We need permission to save photos</string>
<key>NSFaceIDUsageDescription</key>
<string>We use Face ID to protect your app</string>
```

### 4️⃣ Run the App

```bash
# For development
flutter run

# Build APK
flutter build apk --release

# Build App Bundle
flutter build appbundle --release
```

---

## 📱 Usage

### Main Screen
- **Single tap**: View photo/video
- **Long press**: Enable multi-selection mode
- **Pull down**: Refresh list
- **3 taps on Library**: Open hidden folder

### Video Player
- **Single tap**: Show/hide controls
- **Double tap left**: Rewind 10 seconds
- **Double tap right**: Forward 10 seconds
- **Vertical swipe left**: Adjust brightness
- **Vertical swipe right**: Adjust volume

### Subtitle Settings
1. Open video
2. Tap subtitle icon
3. Select SRT/VTT file
4. Customize appearance (color, size, position)

### App Lock
1. Go to Settings
2. Enable "App Lock"
3. Enter passcode (minimum 4 digits)
4. Enable biometric (optional)

---

## 📂 Project Structure

```
mosa-gallery/
├── lib/
│   ├── main.dart                      # Entry point
│   ├── home.dart                      # Main page and navigation
│   ├── all_media_page.dart           # All media page
│   ├── collections_page.dart         # Albums page
│   └── pages/
│       ├── media_viewer_page.dart    # Photo/video viewer
│       ├── video_player_screen.dart  # Advanced player
│       ├── sub_setting.dart          # Subtitle settings
│       ├── setting.dart              # App settings
│       ├── app_lock_service.dart     # App lock service
│       ├── hidden_page.dart          # Hidden files page
│       ├── deleted_page.dart         # Recently deleted
│       └── welcome_screen.dart       # Welcome screen
├── android/
│   └── app/
│       └── src/main/
│           ├── AndroidManifest.xml   # Permissions
│           └── kotlin/               # Native code for PIP
├── assets/
│   ├── icon3.png                     # App icon
│   └── test.jpg                      # Test image
├── pubspec.yaml                       # Dependencies
└── README.md                          # This file
```

---

## 🎨 Screenshots

### Main Screen
- Photo and video gallery sorted by date
- 5 different navigation bar designs
- Advanced filters and search

### Video Player
- Modern interface with Glassmorphism effects
- Full subtitle support
- Smooth controls
- PIP mode

### Settings
- App lock and biometric authentication
- Navigation bar customization
- Player settings (speed, rotation, audio)
- Language support

---

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute:

1. Fork the project
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Future Development Ideas
- [ ] Full iOS support
- [ ] Built-in photo editor
- [ ] Video trimming and editing
- [ ] Automatic subtitle download
- [ ] Cloud synchronization
- [ ] Album sharing
- [ ] Face recognition

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Mohamed (MOSAD)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 👨‍💻 Developer

**Mohamed (MOSAD)**

- GitHub: [@M0SAD67](https://github.com/M0SAD67)
- Email: mhmdaldhshwry280@gmail.com

### 🙏 Special Thanks
- **Flutter Team** - Amazing framework
- **Dart Team** - Powerful language
- **Open Source Community** - For the libraries used

---

## 🐛 Known Issues

1. **PIP Mode**: May not work on some custom Android devices
2. **Biometric**: Not available on older devices
3. **Hide Files**: Requires special permissions on Android 11+

---

## 📞 Support & Contact

If you encounter an issue or have a suggestion:

- Open an [Issue](https://github.com/M0SAD67/mosa-gallery/issues) on GitHub
- Email me at [mhmdaldhshwry280@gmail.com](mailto:mhmdaldhshwry280@gmail.com)

---

## 🌟 Support the Project

If you like the project:
- ⭐ Star the project on GitHub
- 🔀 Share the project with friends
- 🐛 Report bugs
- 💡 Suggest new features

---

<div align="center">

**Made with ❤️ in Egypt**

[![GitHub](https://img.shields.io/badge/GitHub-M0SAD67-181717?style=for-the-badge&logo=github)](https://github.com/M0SAD67)

</div>
