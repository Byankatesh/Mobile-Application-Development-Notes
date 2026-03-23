📌 Introduction

In Android, some tasks need to run in the background without user interaction, such as syncing data, downloading files, or playing music.
These tasks are handled using Services and scheduling components.

🧩 What is a Service?

👉 A Service is a component that runs in the background without a user interface.

📌 Examples:
Music playback
File download
Data synchronization
🔄 Types of Services
Foreground Service
Background Service
🔹 1. Background Service

👉 Runs in the background (no UI)

💻 Example Code
public class MyService extends Service {

    @Override
    public int onStartCommand(Intent intent, int flags, int startId) {
        // Background task
        return START_STICKY;
    }

    @Override
    public IBinder onBind(Intent intent) {
        return null;
    }
}
🔹 2. Foreground Service ⭐

👉 Runs with a visible notification (important tasks)

📌 Example:
Music player
Location tracking
💻 Example Code
Notification notification = new NotificationCompat.Builder(this, "channel")
        .setContentTitle("Service Running")
        .setSmallIcon(R.drawable.ic_launcher)
        .build();

startForeground(1, notification);
⏱️ JobScheduler

👉 Used to schedule background tasks efficiently

💻 Example Code
JobInfo jobInfo = new JobInfo.Builder(1,
        new ComponentName(this, MyJobService.class))
        .setRequiredNetworkType(JobInfo.NETWORK_TYPE_ANY)
        .build();

JobScheduler scheduler = getSystemService(JobScheduler.class);
scheduler.schedule(jobInfo);
🔁 WorkManager ⭐ (Recommended)

👉 Modern and recommended API for background tasks

💻 Example Code
WorkManager workManager = WorkManager.getInstance(this);

OneTimeWorkRequest workRequest =
        new OneTimeWorkRequest.Builder(MyWorker.class).build();

workManager.enqueue(workRequest);
💻 Worker Class
public class MyWorker extends Worker {

    public MyWorker(Context context, WorkerParameters params) {
        super(context, params);
    }

    @Override
    public Result doWork() {
        // Background work here
        return Result.success();
    }
}
🏗️ Example Flow
User Action → Trigger Service  
Service → Run in background  
WorkManager → Schedule task  
Notification → Foreground service  
⭐ Best Practices
Use WorkManager for most background tasks
Use Foreground Service for long-running tasks
Avoid heavy work on main thread
Handle battery optimization
🚀 Conclusion

Background and foreground services allow Android apps to perform tasks efficiently without interrupting the user experience.

💡 Quick Revision
Service → Background task  
Foreground Service → With notification  
JobScheduler → Schedule jobs  
WorkManager → Recommended API  
