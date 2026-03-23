📌 Introduction

In Android, an Activity represents a single screen with a user interface.
It is one of the core components used to build interactive mobile applications.

🧩 What is an Activity?

An Activity is a screen in an Android app where users can interact.

📌 Examples:
Login Screen
Home Screen
Profile Screen

👉 Each screen = One Activity

🏗️ Structure of Activity

An Activity typically contains:

UI layout (XML)
Logic (Java/Kotlin code)
Lifecycle methods
🔄 Android Activity Lifecycle

The Activity Lifecycle defines how an activity behaves from creation to destruction.

🖼️ Activity Lifecycle Diagram
🔑 Lifecycle Methods
1️⃣ onCreate()
Called when activity is first created
Used to initialize UI
setContentView() is used here
2️⃣ onStart()
Activity becomes visible
3️⃣ onResume()
Activity comes to foreground
User can interact
4️⃣ onPause()
Activity partially hidden
Save user data
5️⃣ onStop()
Activity no longer visible
6️⃣ onRestart()
Called when activity restarts
7️⃣ onDestroy()
Activity is destroyed
Cleanup resources
🔄 Lifecycle Flow
onCreate() → onStart() → onResume()
   ↓
[Running Activity]
   ↓
onPause() → onStop() → onDestroy()
💻 Basic Example Code
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}

@Override
protected void onPause() {
    super.onPause();
}

@Override
protected void onDestroy() {
    super.onDestroy();
}
⚡ State Changes

Activity state changes occur when:

User presses Home button
User switches apps
Incoming call
Screen rotation
⭐ Best Practices
Save important data in onPause()
Release resources in onStop() / onDestroy()
Avoid heavy tasks in onCreate()
Handle screen rotation properly
🚀 Conclusion

Understanding the Activity Lifecycle is essential for managing app behavior efficiently and improving user experience in Android applications.
