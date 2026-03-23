📌 Introduction

In Android, UI components (widgets) are used to create interactive user interfaces.
They allow users to input data, view information, and perform actions.

🧩 What are Widgets?

Widgets are basic UI elements used to design the app interface.

📌 Examples:
TextView
EditText
Button
ImageView
🔹 1. TextView

Used to display text on the screen

💻 Example Code

    <TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello World"
    android:textSize="18sp"/>
🔹 2. EditText

Used to take input from the user

💻 Example Code  

    <EditText
    android:id="@+id/editName"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Enter your name"/>
🔹 3. Button

Used to perform actions when clicked

💻 Example Code

    <Button
    android:id="@+id/btnSubmit"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Submit"/>
🔹 4. ImageView

Used to display images

💻 Example Code

    <ImageView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:src="@drawable/sample_image"/>
🏗️ Example: Simple Form UI
📌 Layout Structure
[ Enter Name        ]
[ Enter Email       ]
[ Submit Button     ]
[     Image         ]
💻 Complete XML Code

    <LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:text="User Form"
        android:textSize="20sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <EditText
        android:id="@+id/name"
        android:hint="Enter Name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <EditText
        android:id="@+id/email"
        android:hint="Enter Email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/btnSubmit"
        android:text="Submit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <ImageView
        android:src="@drawable/sample_image"
        android:layout_width="100dp"
        android:layout_height="100dp"/>

</LinearLayout>
⚡ Interaction (Java Example)
Button btn = findViewById(R.id.btnSubmit);
EditText name = findViewById(R.id.name);

btn.setOnClickListener(v -> {
    String userName = name.getText().toString();
});
⭐ Best Practices
Use meaningful IDs
Keep UI simple
Use proper spacing (margin/padding)
Validate user input
🚀 Conclusion

Widgets like TextView, EditText, Button, and ImageView are essential for building interactive Android applications. and handling user input effectively.
Widgets like TextView, EditText, Button, and ImageView are essential for building interactive Android applications and handling user input effectively.
