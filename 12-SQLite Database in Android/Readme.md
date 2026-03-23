📌 Introduction

In Android, SQLite is used for local data storage.
It allows applications to store, retrieve, update, and delete data efficiently.

🧩 What is SQLite?

👉 SQLite is a lightweight, embedded database
👉 No server required
👉 Data is stored locally in the device

🔄 CRUD Operations

CRUD stands for:

Create → Insert data  
Read → Fetch data  
Update → Modify data  
Delete → Remove data  
🏗️ SQLiteOpenHelper Class

👉 Used to manage database creation and version management

💻 Database Helper Class
public class DBHelper extends SQLiteOpenHelper {

    private static final String DB_NAME = "StudentDB";
    private static final int DB_VERSION = 1;

    public DBHelper(Context context) {
        super(context, DB_NAME, null, DB_VERSION);
    }

    @Override
    public void onCreate(SQLiteDatabase db) {
        db.execSQL("CREATE TABLE student(id INTEGER PRIMARY KEY, name TEXT)");
    }

    @Override
    public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
        db.execSQL("DROP TABLE IF EXISTS student");
        onCreate(db);
    }
}
➕ CREATE (Insert Data)
public void insertData(String name) {
    SQLiteDatabase db = this.getWritableDatabase();
    ContentValues values = new ContentValues();
    values.put("name", name);
    db.insert("student", null, values);
}
📖 READ (Fetch Data)
public Cursor getData() {
    SQLiteDatabase db = this.getReadableDatabase();
    return db.rawQuery("SELECT * FROM student", null);
}
✏️ UPDATE Data
public void updateData(int id, String name) {
    SQLiteDatabase db = this.getWritableDatabase();
    ContentValues values = new ContentValues();
    values.put("name", name);
    db.update("student", values, "id=?", new String[]{String.valueOf(id)});
}
❌ DELETE Data
public void deleteData(int id) {
    SQLiteDatabase db = this.getWritableDatabase();
    db.delete("student", "id=?", new String[]{String.valueOf(id)});
}
🏗️ Example Flow
Insert → Store data  
Fetch → Show data  
Update → Modify data  
Delete → Remove data  
⭐ Best Practices
Use SQLiteOpenHelper class
Close database after use
Use parameterized queries (avoid SQL injection)
Keep database operations efficient
🚀 Conclusion

SQLite helps in managing local data efficiently in Android apps and supports all CRUD operations for data handling.

💡 Quick Revision
SQLite → Local database  
CRUD → Create, Read, Update, Delete  
Helper Class → Manage DB  
