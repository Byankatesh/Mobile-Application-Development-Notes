📌 Introduction

In Android, a Fragment represents a reusable portion of UI inside an Activity.
It helps in building modular and flexible user interfaces.

🧩 What is a Fragment?

👉 Fragment = Part of an Activity UI

📌 Example:
Activity = Full Screen
Fragment = Section of Screen

👉 One Activity can contain multiple Fragments

🏗️ Why Use Fragments?
Reusable UI components
Better UI for tablets & large screens
Modular design
Easier maintenance
🔄 Fragment Lifecycle

Fragments have their own lifecycle similar to Activity.

📌 Lifecycle Flow
onAttach()
onCreate()
onCreateView()
onActivityCreated()
onStart()
onResume()
   ↓
[Running]
   ↓
onPause()
onStop()
onDestroyView()
onDestroy()
onDetach()
🔑 Important Methods
onCreate() → Initialize fragment
onCreateView() → Inflate layout
onDestroyView() → Clean UI
onDetach() → Fragment removed
🛠️ Creating a Fragment
💻 Java Class
public class MyFragment extends Fragment {

    @Override
    public View onCreateView(LayoutInflater inflater,
                             ViewGroup container,
                             Bundle savedInstanceState) {
        return inflater.inflate(R.layout.fragment_layout, container, false);
    }
}
💻 XML Layout (fragment_layout.xml)

    <TextView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:text="Hello Fragment"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
🔄 Fragment Transactions

👉 Used to manage fragments dynamically

➕ Add Fragment
getSupportFragmentManager()
    .beginTransaction()
    .add(R.id.container, new MyFragment())
    .commit();
🔁 Replace Fragment
getSupportFragmentManager()
    .beginTransaction()
    .replace(R.id.container, new MyFragment())
    .commit();
❌ Remove Fragment
getSupportFragmentManager()
    .beginTransaction()
    .remove(fragment)
    .commit();
🔗 Communication (Fragment ↔ Activity)

👉 Fragment communicates with Activity using Interface

💻 Example
public interface OnDataSend {
    void sendData(String data);
}

👉 Activity implements this interface

🏗️ Example Structure
Activity
  ├── Fragment A
  ├── Fragment B
⭐ Best Practices
Use Fragment for reusable UI
Avoid heavy logic inside Fragment
Use ViewBinding / DataBinding
Manage lifecycle properly
🚀 Conclusion

Fragments help in building modular, flexible, and reusable UI components in Android applications.

💡 Quick Revision
Fragment → Part of Activity  
Lifecycle → Similar to Activity  
Transaction → Add / Replace / Remove  
Communication → Interface
