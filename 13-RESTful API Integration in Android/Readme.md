📌 Introduction

In modern app development, applications communicate with servers using APIs.
In Android, RESTful APIs are widely used to fetch and send data over the internet.

🌍 What is a Web Service?

👉 A web service allows communication between client (app) and server
👉 Data is usually exchanged in JSON format

🔄 REST vs SOAP
Feature	REST	SOAP
Type	Lightweight	Heavy
Format	JSON	XML
Speed	Fast	Slower
Usage	Modern apps	Enterprise systems
🧪 Testing API using Postman

👉 Postman is used to test APIs before integration

Steps:
Open Postman
Enter API URL
Select method (GET, POST)
Click Send
View JSON response
📦 JSON Response Example
{
  "id": 1,
  "name": "John",
  "email": "john@example.com"
}
🔧 API Integration using Retrofit ⭐

👉 Retrofit is a popular library for API calls

🛠️ Step 1: Add Dependency
implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
🧩 Step 2: Create API Interface
public interface ApiService {

    @GET("users")
    Call<List<User>> getUsers();
}
⚙️ Step 3: Create Retrofit Instance
Retrofit retrofit = new Retrofit.Builder()
        .baseUrl("https://api.example.com/")
        .addConverterFactory(GsonConverterFactory.create())
        .build();

ApiService api = retrofit.create(ApiService.class);
📡 Step 4: Make API Call
api.getUsers().enqueue(new Callback<List<User>>() {
    @Override
    public void onResponse(Call<List<User>> call, Response<List<User>> response) {
        List<User> users = response.body();
    }

    @Override
    public void onFailure(Call<List<User>> call, Throwable t) {
        t.printStackTrace();
    }
});
🔄 Alternative: Volley

👉 Volley is another library for network requests

💻 Volley Example
String url = "https://api.example.com/users";

RequestQueue queue = Volley.newRequestQueue(this);

JsonObjectRequest request = new JsonObjectRequest(
        Request.Method.GET, url, null,
        response -> {
            // handle response
        },
        error -> {
            // handle error
        });

queue.add(request);
⭐ Best Practices
Use Retrofit for clean code
Handle errors properly (onFailure)
Use background threads
Check internet permission
🚀 Conclusion

RESTful APIs allow Android apps to communicate with servers efficiently and handle dynamic data using JSON responses.

💡 Quick Revision
REST → Fast API  
SOAP → Heavy API  
Retrofit → Modern library  
Volley → Alternative  
JSON → Data format  
