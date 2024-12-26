# Godot Engine Optimization for 2D Android Games

## Overview
Welcome to the Godot Engine Optimization repository. This repository includes all the necessary files and resources to help you optimize your Godot 2D games for Android, reducing the APK size significantly. Please follow along with the provided files and abstract steps to make it more efficient for your games.

Complete detailed steps on [Medium](https://medium.com/@nikhil2003verma/how-i-reduced-godot-game-size-from-250mb-to-23mb-for-android-8858e7287d8e)

## Contents
- **custom.py**: Custom build script for optimizing the Godot engine.
- **forced classes.txt**: List of forced classes to include in the build.
- **APKs & AARs**: Pre-built Android debug and release APKs and AARs.
- **Source Template**: Optimized Godot engine source template.

## Getting Started

### Prerequisites
- Ensure you have Godot installed. Download the version you are using for your game.
- Familiarize yourself with the [Compiling for Android](https://docs.godotengine.org/en/stable/development/compiling/compiling_for_android.html) guide on Godot Docs.

### Clone the Repository
```sh
git clone https://github.com/NIKHIL0VERMA/GodotEngine-Optimization.git
cd GodotEngine-Optimization
```

### Setup Environment
1. **Download Godot Source Code**:
   ```sh
   git clone https://github.com/godotengine/godot.git -b 4.1.3-stable
   ```

2. **Copy Configuration Files**:
   - Copy `custom.py` and `forced_classes.txt` to the root of the Godot source directory.

### Build Instructions

#### Using Custom.py
1. **Navigate to Godot Source Directory**:
   ```sh
   cd godot
   ```

2. **Build Debug Templates**:
   ```sh
   scons target=template_debug
   ```

3. **Build Release Templates**:
   ```sh
   scons target=template_release
   ```

4. **For Maximum Device Support**:
   ```sh
   scons -j4 target=template_release arch=arm32
   scons -j4 target=template_release arch=arm64
   ```

### Generate Engine APKs
1. **Navigate to Android Directory**:
   ```sh
   cd platform/android/java
   ```

2. **Generate APKs**:
   - **On Windows**:
     ```sh
     .\gradlew generateGodotTemplates
     ```
   - **On Linux and macOS**:
     ```sh
     ./gradlew generateGodotTemplates
     ```

### Using Optimized Templates
Follow the guide on using [Godot templates](https://docs.godotengine.org/en/stable/development/compiling/compiling_for_android.html#using-the-templates) for detailed instructions on applying the optimized templates to your project.

## General Optimization Tips
- Remove unused assets and compress textures and audio files.
- Use sprite atlases to combine multiple textures into a single image.
- Strip unused features and modules during the build process.
- Use ProGuard for shrinking, optimizing, and obfuscating code.

## Contributing
Feel free to contribute by opening issues, submitting pull requests, or providing feedback. Let's optimize together!

## License
This project is licensed under the MIT License.

## Contact
Reach out to me on [Twitter](https://twitter.com/NIKHIL0VERMA) or [LinkedIn](https://linkedin.com/in/nikhil2003verma) for any queries or feedback.
