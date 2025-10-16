### What is Broadcast Receivers?
- Act as **application components** and also **interprocess communication mechanisms**.
- Defined in **AndroidManifest.xml**:

```xml
<manifest ...>
    <application ...>
        <receiver android:name=".MyBroadcastReceiver">
            <intent-filter>
                <action android:name="" />
                <action android:name="" />
            </intent-filter>
        </receiver>
    </application>
</manifest>
```

---

### 1. Application Components
- Designed to respond to **system-wide events** or **custom events** broadcasted by other applications.  
- Work like a **messaging system** between different components across the Android ecosystem.  

---

### 2. Interprocess Communication (IPC)
- Allow the same or different apps to **communicate with each other**.  
- To use it: extend the **BroadcastReceiver** class and override **onReceive()**.  

```java
public class MyBroadcastReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        String action = intent.getAction();

        if (action != null) {
            switch (action) {
                case Intent.ACTION_POWER_CONNECTED:
                    // Handle power connected event
                    break;
                case Intent.ACTION_POWER_DISCONNECTED:
                    // Handle power disconnected event
                    break;
                default:
                    // Handle other actions
                    break;
            }
        }
    }
}
```

---

### 3. Types of Broadcast Receivers
- **Public (implicit broadcast)**  
  - Sent by the system or apps, visible to all apps.  
  - Example: **battery low / charging**.  

- **Private (explicit broadcast)**  
  - Sent to a specific component or application.  
  - Other apps don’t see it.  
  - Example: YouTube app broadcasting an intent internally to notify a component when internet is available.  

---

## Question 
Since Broadcast Receivers are a way of IPC, what’s the real difference?

1. **IPC**  
   - Low-level, one-to-one communication.  
   - Queues messages.  
   - Shares structured data (e.g., contacts, DB access).  

2. **Broadcast Receivers**  
   - One-to-many communication.  
   - Works best for **events** (e.g., battery low, network change).  

---

### Methods for Sending Broadcasts
1. **sendOrderedBroadcast(Intent, String)**  
   - Sends to one receiver at a time in order.  

2. **sendBroadcast(Intent)**  
   - Sends to all receivers in an undefined order.  

3. **LocalBroadcastManager.sendBroadcast(intent)**  
   - Sends broadcast inside your app only.  
   - Deprecated since **API 28**, replaced by **LiveData**, **Flow**, or **EventBus**.  

---

### Attacks
- Exported broadcast receivers