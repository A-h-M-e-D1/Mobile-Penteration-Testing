### What is Intents
- Used to send a messaging object from the application or Android system to request an action from another component such as (Services, Activities, Broadcast Receivers).

### Three use cases for Intents
1. **Start An Activity**
- The Intents are used to launch a new Activity.
- Used to pass data between components.

2. **Start a Service**
- It is used to start or bind a specific service in the background.

3. **Delivery Broadcasts**
- Used to send broadcast messages to specific applications or components.
- Intents here are the messages that broadcasts send.
- We can carry data between components in the form of key-value pairs, called ```extras```.
  ```java
  intent.putExtra("key", "value");
  ```

### Intent IPC Types
1. **Explicit Intent**
- Used when I know that I need specific components (Service, Broadcast Receiver, Activity) to handle it.
- EX: Move from one screen to another in the same application.

2. **Implicit Intent**
- Here I don't know the target component I want to work with, but I know the action I want to do.
- To create an implicit Intent, we must specify the action and the data (URI).
  ```java
   Intent intent = new Intent(Intent.ACTION_VIEW);
   intent.setData(Uri.parse("https://www.example.com"));
   startActivity(intent);
   ````

