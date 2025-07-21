# Stampede - Frontend Package

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This package provides a suite of reusable Flutter widgets, themes, and design utilities for the Stampede School App project. It is designed to be a flexible UI kit that can be styled to fit any school's branding, accelerating the development of beautiful, consistent, and responsive school-specific mobile applications.

This package is part of a multi-repository project:
*   **`frontend_package` (This repo):** The reusable UI kit.
*   **`backend_package`:** Handles data models, state management, and services.
*   **`northside-app`:** A complete implementation and example of how to use these packages.

## 🧙 Features
*   **Reusable Widgets:** A collection of common UI elements like headers, sheets, and cards, ready to be used.
*   **Customizable Theme:** Easily configure colors, fonts, and styles to match your school's brand identity.
*   **Consistent Design:** Pre-defined constants for padding, border radius, and shadows ensure a uniform look and feel.
*   **Responsive Utilities:** Helpers for creating layouts that adapt to different screen sizes.

## 🧑‍💻 Getting Started

Follow these two steps to get the package running in your project.

### 1. Installation

Add the package to your `pubspec.yaml` file as a git dependency.

```yaml
dependencies:
  flutter:
    sdk: flutter
  
  frontend_package:
    git:
      url: https://github.com/NCP-Stampede/frontend_package.git
      ref: main # You can also pin to a specific version tag
```

Then, run flutter pub get in your terminal.

### 2. Basic Usage

Now you can import components from the package and use them in your app.

#### Applying a Custom Theme

The most powerful feature is the ability to provide your own brand colors. In your main.dart file, import app_theme.dart and use the buildTheme method.

```
// main.dart
import 'package:flutter/material.dart';
import 'package:frontend_package/core/theme/app_theme.dart';

// Define your school's specific colors
const mySchoolPrimaryColor = Color(0xFFB71C1C); // Example: A deep red
const mySchoolSecondaryColor = Color(0xFFFFEB3B); // Example: A bright yellow
const mySchoolBackgroundColor = Color(0xFFF5F5F5);

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My School App',
      // Pass your colors to the theme builder from the package
      theme: AppTheme.buildTheme(
        primaryColor: mySchoolPrimaryColor,
        secondaryColor: mySchoolSecondaryColor,
        backgroundColor: mySchoolBackgroundColor,
      ),
      home: YourHomePage(),
    );
  }
}
```

#### Using a Widget

To use a widget from this package, simply import it and add it to your widget tree.

```
// my_screen.dart
import 'package:flutter/material.dart';
import 'package:frontend_package/widgets/shared_header.dart'; // Import the widget

class MyScreen extends StatelessWidget {
  const MyScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return const Scaffold(
      body: Column(
        children: [
          // Use the widget directly!
          SharedHeader(title: 'My Awesome Screen'),
          // ... rest of your screen
        ],
      ),
    );
  }
}
```

### 3. Contributing

Contributions are welcome! If you have an idea for a new reusable widget or want to improve an existing one, please feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details. 
