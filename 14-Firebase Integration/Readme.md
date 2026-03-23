📌 Introduction

In Android, Firebase is used to build backend features like database and authentication without managing servers.

🌐 What is Firebase?

👉 Firebase is a Backend-as-a-Service (BaaS) platform provided by Google

👉 It provides:

Realtime Database / Firestore
Authentication
Cloud Storage
🛠️ Firebase Setup
🔹 Step 1: Create Project
Go to Firebase Console
Click Add Project
Enter project name
Create project
🔹 Step 2: Connect App
Select Android app
Enter package name
Download google-services.json
Place it inside app/ folder
🔹 Step 3: Add Dependencies
implementation 'com.google.firebase:firebase-auth:22.0.0'
implementation 'com.google.firebase:firebase-database:20.0.0'
🔐 Firebase Authentication (Email/Password)

👉 Used to login/signup users securely

💻 Register User
FirebaseAuth auth = FirebaseAuth.getInstance();

auth.createUserWithEmailAndPassword(email, password)
    .addOnCompleteListener(task -> {
        if (task.isSuccessful()) {
            // Registration success
        }
    });
💻 Login User
auth.signInWithEmailAndPassword(email, password)
    .addOnCompleteListener(task -> {
        if (task.isSuccessful()) {
            // Login success
        }
    });
🗄️ Firebase Realtime Database

👉 Stores data in JSON format (real-time updates)

💻 Insert Data
DatabaseReference ref = FirebaseDatabase.getInstance().getReference("users");

ref.push().setValue("Hello Firebase");
💻 Read Data
ref.addValueEventListener(new ValueEventListener() {
    @Override
    public void onDataChange(DataSnapshot snapshot) {
        String value = snapshot.getValue(String.class);
    }

    @Override
    public void onCancelled(DatabaseError error) {
    }
});
🔥 Firestore (Alternative)

👉 Modern database (structured + scalable)

💻 Insert Data
FirebaseFirestore db = FirebaseFirestore.getInstance();

Map<String, Object> user = new HashMap<>();
user.put("name", "John");

db.collection("users").add(user);
💻 Read Data
db.collection("users").get().addOnSuccessListener(query -> {
    for (DocumentSnapshot doc : query) {
        String name = doc.getString("name");
    }
});
⭐ Best Practices
Use Firestore for scalable apps
Validate user input
Handle errors properly
Use secure authentication
🚀 Conclusion

Firebase simplifies backend development by providing authentication and real-time databases, making Android apps faster and more efficient.

💡 Quick Revision
Firebase → Backend service  
Auth → Login/Register  
Realtime DB → JSON data  
Firestore → Structured DB  
