📌 Introduction

In Android, advanced input controls are used to handle user selections and choices efficiently.
These components improve user interaction and help in building dynamic forms.

🧩 What are Advanced Input Controls?

These are UI components that allow users to select options easily.

📌 Examples:
RadioGroup & RadioButton
CheckBox
Spinner
🔹 1. RadioGroup & RadioButton

👉 Used when user can select only one option

📌 Example:

Gender selection (Male / Female)

💻 XML Code

    <RadioGroup
    android:layout_width="wrap_content"
    android:layout_height="wrap_content">

    <RadioButton
        android:id="@+id/male"
        android:text="Male"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <RadioButton
        android:id="@+id/female"
        android:text="Female"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

</RadioGroup>
⚡ Java Code
RadioGroup group = findViewById(R.id.radioGroup);

int selectedId = group.getCheckedRadioButtonId();
RadioButton selected = findViewById(selectedId);
String value = selected.getText().toString();
🔹 2. CheckBox

👉 Used when user can select multiple options

📌 Example:

Hobbies (Reading, Music, Sports)

💻 XML Code

    <CheckBox
    android:id="@+id/reading"
    android:text="Reading"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>

    <CheckBox
    android:id="@+id/music"
    android:text="Music"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"/>
⚡ Java Code
CheckBox reading = findViewById(R.id.reading);

if (reading.isChecked()) {
    // Do something
}
🔹 3. Spinner

👉 Used to select one option from a dropdown list

📌 Example:

Select City

💻 XML Code

    <Spinner
    android:id="@+id/spinner"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
⚡ Java Code
Spinner spinner = findViewById(R.id.spinner);

String[] items = {"Delhi", "Mumbai", "Indore"};

ArrayAdapter<String> adapter = new ArrayAdapter<>(
        this,
        android.R.layout.simple_spinner_item,
        items
);

adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
spinner.setAdapter(adapter);
🏗️ Example: Combined Form UI
📌 Layout Structure
[ Select Gender (Radio) ]
[ Select Hobbies (Checkbox) ]
[ Select City (Spinner) ]
[ Submit Button ]
💻 Complete XML Code

    <LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:padding="16dp"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <RadioGroup
        android:id="@+id/radioGroup"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <RadioButton
            android:id="@+id/male"
            android:text="Male"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

        <RadioButton
            android:id="@+id/female"
            android:text="Female"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>
    </RadioGroup>

    <CheckBox
        android:id="@+id/reading"
        android:text="Reading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <CheckBox
        android:id="@+id/music"
        android:text="Music"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <Spinner
        android:id="@+id/spinner"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:text="Submit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

</LinearLayout>
⭐ Best Practices
Use RadioGroup for single selection
Use CheckBox for multiple selection
Use Spinner for dropdown lists
Validate user input before submission
🚀 Conclusion

Advanced input controls like RadioButton, CheckBox, and Spinner help in creating interactive and user-friendly Android applications.

💡 Quick Revision
RadioButton → Single choice  
CheckBox → Multiple choice  
Spinner → Dropdown selection
