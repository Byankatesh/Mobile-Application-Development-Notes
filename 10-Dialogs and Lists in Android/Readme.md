📌 Introduction

In Android, dialogs and list-based components are used to interact with users and display data efficiently.
They help in showing messages, taking input, and presenting items in list or grid format.

🧩 Components Covered
AlertDialog
AutoCompleteTextView
ListView
GridView
Toast
Snackbar
🔹 1. AlertDialog

👉 Used to show popup messages or confirmations

📌 Example:

"Are you sure you want to exit?"

💻 Java Code
AlertDialog.Builder builder = new AlertDialog.Builder(this);
builder.setTitle("Exit");
builder.setMessage("Are you sure you want to exit?");
builder.setPositiveButton("Yes", (dialog, which) -> finish());
builder.setNegativeButton("No", null);
builder.show();
🔹 2. AutoCompleteTextView

👉 Shows suggestions while typing

💻 XML Code

    <AutoCompleteTextView
    android:id="@+id/autoText"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Enter city"/>
💻 Java Code
AutoCompleteTextView textView = findViewById(R.id.autoText);

String[] cities = {"Delhi", "Mumbai", "Indore"};

ArrayAdapter<String> adapter = new ArrayAdapter<>(
        this,
        android.R.layout.simple_dropdown_item_1line,
        cities
);

textView.setAdapter(adapter);
🔹 3. ListView

👉 Displays items in a vertical list

💻 XML Code

    <ListView
    android:id="@+id/listView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
💻 Java Code
ListView listView = findViewById(R.id.listView);

String[] items = {"Apple", "Banana", "Mango"};

ArrayAdapter<String> adapter = new ArrayAdapter<>(
        this,
        android.R.layout.simple_list_item_1,
        items
);

listView.setAdapter(adapter);
🔹 4. GridView

👉 Displays items in grid format

💻 XML Code

    <GridView
    android:id="@+id/gridView"
    android:numColumns="2"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
💻 Java Code
GridView gridView = findViewById(R.id.gridView);

String[] items = {"A", "B", "C", "D"};

ArrayAdapter<String> adapter = new ArrayAdapter<>(
        this,
        android.R.layout.simple_list_item_1,
        items
);

gridView.setAdapter(adapter);
🔹 5. Toast

👉 Shows short message for user feedback

💻 Java Code
Toast.makeText(this, "Saved Successfully", Toast.LENGTH_SHORT).show();
🔹 6. Snackbar

👉 Modern alternative of Toast (with action)

💻 Java Code
Snackbar.make(findViewById(android.R.id.content),
        "Item Deleted",
        Snackbar.LENGTH_LONG)
        .setAction("UNDO", v -> {
            // undo action
        })
        .show();
🏗️ Example Flow
Click Button → Show Dialog  
Type → Show Suggestions  
Select Item → Show Toast  
Delete → Show Snackbar  
⭐ Best Practices
Use AlertDialog for confirmations
Use Snackbar for actions (UNDO)
Avoid overusing Toast
Use ListView/GridView for displaying data
🚀 Conclusion

Dialogs and list components improve user interaction and provide better feedback in Android applications.

💡 Quick Revision
AlertDialog → Popup  
AutoCompleteTextView → Suggestions  
ListView → List  
GridView → Grid  
Toast → Short message  
Snackbar → Action message
