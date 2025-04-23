# Android App Renamer

A Bash script for renaming an Android application in a **Gradle Kotlin DSL** (`*.kts`) project. This tool updates the app name, package name, and all relevant configuration and source files in a typical Android Studio project structure.

## 🛠 Purpose

Renaming an Android app manually can be tedious and error-prone. This script automates the process by:

- Updating the `rootProject.name` in `settings.gradle.kts`
- Changing `applicationId` and `namespace` in `build.gradle.kts`
- Renaming package declarations in Kotlin/Java files
- Moving the source and test directories to reflect the new package structure
- Modifying string resources like `app_name`
- Adjusting Android Studio's `.iml` and run configurations

## 📦 Suitable For

Projects using:

- Android Studio
- Kotlin or Java
- Gradle Kotlin DSL (`*.kts`)
- Standard folder structure:
  ```
  ./app/src/main/java/com/example/yourapp
  ./app/src/test/java/...
  ./app/src/androidTest/java/...
  ```

## 🚀 How to Use

1. Clone or download this script into the root of your Android project.
2. Ensure the script has executable permissions:
   ```bash
   chmod +x rename_app.sh
   ```
3. Run the script:
   ```bash
   ./rename_app.sh
   ```
4. Enter the new application name when prompted (e.g. `mynewapp`).
   - The package will be automatically updated to: `com.example.mynewapp`.

5. After the script finishes:
   - Open Android Studio
   - Run **Clean Project**
   - Run **Rebuild Project**
   - Sync Gradle

## 📂 Example

If your current app name is `weatherapp` and you run the script with:

```bash
Enter new application name: notes
```

Then:
- `rootProject.name` changes to `notes`
- `applicationId` and `namespace` become `com.example.notes`
- All package declarations and folders are updated accordingly

## ⚠️ Warnings

- Make sure to **commit your code** or back it up before running the script.
- This script assumes a fairly standard project layout. Custom setups may require adjustments.
- Does **not** rename the folder containing the entire project (e.g. if your repo is called `weatherapp`).

## 📄 License

GPL-3.0 license
