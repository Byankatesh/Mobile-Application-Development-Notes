📌 Introduction

In Android development, understanding the project structure is essential for organizing files and managing application components effectively.

🏗️ Android Project Structure

A typical Android project in Android Studio consists of the following main components:

📁 Project Structure Overview
🔑 Main Folders and Files
1️⃣ app/
Main module of the project
Contains all source code and resources
2️⃣ java/ or kotlin/
Contains application source code
Includes Activities, Fragments, and classes
3️⃣ res/ (Resources)
Contains UI and resources:
layout/ → XML UI design
drawable/ → images and icons
values/ → colors, strings, styles
4️⃣ AndroidManifest.xml
Most important configuration file
Declares app components and permissions
5️⃣ Gradle Scripts
Used for build configuration
Manages dependencies and libraries
📄 AndroidManifest.xml

The AndroidManifest.xml file provides essential information about the app to the Android system.

🧩 Role of AndroidManifest.xml
Declares all Activities
Defines permissions (Internet, Camera, etc.)
Specifies app name, icon
Sets launcher activity
🖼️ Manifest File Structure
💻 Basic Example of AndroidManifest.xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.app">

    <application
        android:allowBackup="true"
        android:label="MyApp"
        android:theme="@style/Theme.App">

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>
</manifest>
⚡ Important Elements
🔹 <manifest>
Root element
Defines package name
🔹 <application>
Contains app-level settings
🔹 <activity>
Declares an activity
🔹 <intent-filter>
Defines how activity is launched
⭐ Key Points
Every Android app must have a Manifest file
Activities must be declared in Manifest
Permissions are defined here
Controls app configuration
🚀 Conclusion

Understanding the Android project structure and the role of AndroidManifest.xml helps developers efficiently manage app components and ensure smooth application execution.
